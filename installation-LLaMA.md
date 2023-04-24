## LLaMA installation on Windows

**Step 1. Install Visual Studio**
On windows, you need to install Visual Studio before installing Dalai.

When installing Visual Studio, make sure to check the 3 options as highlighted below:

- Python development
- Node.js development
- Desktop development with C++
![image](https://user-images.githubusercontent.com/123748177/233933351-db22dafc-38d9-484c-a146-967de3912a6c.png)

**Step 2. Install models**
IMPORTANT

On Windows, make sure to run all commands in cmd.

DO NOT run in powershell. Powershell has unnecessarily strict permissions and makes the script fail silently.

Currently supported engines are llama and alpaca.

Install alpaca
To download alpaca models. Open your cmd application and enter:
```
npx dalai alpaca install 7B
```

Add llama models
To download llama models. Open your cmd application and enter:
```
npx dalai llama install 7B
```
or to download multiple models:
```
npx dalai llama install 7B 13B
```

**Step 3. Run Web UI**
After everything has been installed, run the following command to launch the web UI server (Make sure to run in cmd and not powershell!):
```
npx dalai serve
```
and open http://localhost:3000 in your browser. Have fun!


*Side notes:* 
https://github.com/cocktailpeanut/dalai

code: C:\Users\Mkhao\AppData\Local\npm-cache\_npx\3c737cbb02d79cc9\node_modules\dalai

Changes: let [Core, Model] = req.model.split(".") to ['llama', '7B']
