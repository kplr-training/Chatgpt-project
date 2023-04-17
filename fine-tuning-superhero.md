you first need to get an API key from OpenAI and install the Python package openai, which can be quickly done via pip.

For the API key from OpenAI:

- go to https://platform.openai.com/account/api-keys ,
- create an account,
- click on ‘Create new secret key’ and
- do a copy of the key.

PS: The key is a long string of characters starting with ‘sk-’. Make sure you keep it secret! 

Now that we have our key and Python package, it is time to think about the data we need to fine-tune. 
First, we need a file of examples for fine-tuning, where each example is a prompt followed by the appropriate completion.

We will build a tool for this demo to create descriptions of imaginary superheroes. In the end, the tool will receive the age, gender, and power of the superhero, and it will automatically produce a description of our superhero.

In the following example, after fine-tuning the model, all we have to say is ’40, woman, Healing ->’, and we will automatically get a description from the model.

![image](https://user-images.githubusercontent.com/123748177/232505660-17f9b35a-4129-4c54-a358-c3b8f4466db6.png)

## Creation of a synthetic set of data for fine-tuning

In some situations, you may have a data set you want to use for fine-tuning. But since I don’t have one, let’s see how to create a synthetic data set with the description of the superheroes directly from GPT-3. The following code will give me a CSV file with examples of prompts and the corresponding completions.

```
import os
import openai
import pandas as pd

openai.api_key = os.getenv("OPENAI_API_KEY")

l_age = ['18', '20', '30', '40', '50', '60', '90']
l_gender = ['man', 'woman']
l_power = ['invisibility', 'read in the thoughts', 'turning lead into gold', 'immortality', 'telepathy', 'teleport', 'flight'] 

f_prompt = "Imagine a complete and detailed description of a {age}-year-old {gender} fictional character who has the superpower of {power}. Write out the entire description in a maximum of 100 words in great detail:"
f_sub_prompt = "{age}, {gender}, {power}"

df = pd.DataFrame()
for age in l_age:
 for gender in l_gender:
  for power in l_power:
   for i in range(3): ## 3 times each
    prompt = f_prompt.format(age=age, gender=gender, power=power)
    sub_prompt = f_sub_prompt.format(age=age, gender=gender, power=power)
    print(sub_prompt)

    response = openai.Completion.create(
     model="text-davinci-003",
     prompt=prompt,
     temperature=1,
     max_tokens=500,
     top_p=1,
     frequency_penalty=0,
     presence_penalty=0
    )
    
    finish_reason = response['choices'][0]['finish_reason']
    response_txt = response['choices'][0]['text']
    
    new_row = {
      'age':age, 
      'gender':gender, 
      'power':power, 
      'prompt':prompt, 
      'sub_prompt':sub_prompt, 
      'response_txt':response_txt, 
      'finish_reason':finish_reason}
    new_row = pd.DataFrame([new_row])
    df = pd.concat([df, new_row], axis=0, ignore_index=True)

df.to_csv("out_openai_completion.csv")
```

- The variable f_prompt contains the following sentence where {age}, {gender}, and {power} are missing.
```
Imagine a complete and detailed description of a {age}-year-old {gender} fictional character who has the superpower of {power}. Write out the entire description in a maximum of 100 words in great detail:
```
- In the first three for loops of the code, we iterate over different values of {age}, {gender}, and {power}. At each step of the loop, we replace the 3 missing variables with different values.
- Then we use the openai.Completion.create function to ask GPT to generate a response to our prompt.

The most important parameters of this function are

- model: The model used to generate the response. OpenAI offers four standard GPT-3 models (ada, babbage, curie, or davinci) that vary in size … and price of use. Here it is davinci — the biggest model.
- prompt: The prompt that we want to fulfill with GPT-3.
- temperature: The temperature is a number between 0 and 1 and controls how much randomness is in the output. We set the temperature to the maximum to allow the model to be as creative as possible in creating the response.
- max_tokens: Defines the maximum length of the response.

- At the end of this script, we have a Pandas table stored in the file out_openai_completion.csv. The two primary columns in this table that interest us are sub_prompt and response_txt.

The sub_prompt will be for example ‘18, man, invisibility’. It contains the three values that were replaced, separated by commas.

The response_txt contains the output of the GPT model.

## Fine-tuning the GPT model

## GPT-3 Fine-Tuning for Superhero Descriptions
The following code retrieves the previously created file out_openai_completion.csv and uses openai to fine-tune a GPT-3 model.
```
import pandas as pd
import openai
import subprocess

df = pd.read_csv("out_openai_completion.csv")

prepared_data = df.loc[:,['sub_prompt','response_txt']]
prepared_data.rename(columns={'sub_prompt':'prompt', 'response_txt':'completion'}, inplace=True)
prepared_data.to_csv('prepared_data.csv',index=False)


## prepared_data.csv --> prepared_data_prepared.json
subprocess.run('openai tools fine_tunes.prepare_data --file prepared_data.csv --quiet'.split())

## Start fine-tuning
subprocess.run('openai api fine_tunes.create --training_file prepared_data_prepared.jsonl --model davinci --suffix "SuperHero"'.split())
```

- First, the content of the file out_openai_completion.csv is loaded into the data frame df. 
- In the data frame df, the columns sub_prompt and response_txt contain examples of input with the corresponding desired response. In the code above, we first extract these two colons and then rename them to prompt and completion, respectively. The resulting data frame is stored in a new file prepared_data.csv containing only these two columns.
- The Python subprocess.run() function runs a command as a subprocess. It is often used to execute external programs as if they were run in a terminal.
- We use subprocess.run() to execute ‘openai tools fine_tunes.prepare_data’. This function takes the input file prepared_data.csv, checks that the data are correct, and produces a JSONL file called prepared_data_prepared.jsonl. A JSONL file is a format that stores each JSON object on a separate line. 
- The fine-tuning of the GPT-3 model is really achieved in the second subprocess.run(), where openai api fine_tunes.create is executed. In this function, we start by giving the name of the JSONL file created just before.
- You will then need to select the model you wish to fine-tune.




