# verify-minify-json

Tools to verify and minify JSON files

<br><br>

## How to:

### *Install*

```bash
sudo git clone --depth 1 https://github.com/tomasfn87/verify-minify-json /usr/local/lib/verify-minify-json && sudo rm -rf /usr/local/lib/verify-minify-json/{.git,README.md,sample*} && sudo ln -s /usr/local/lib/verify-minify-json/minify_json_interactive.sh /usr/local/bin/mjsoni && sudo ln -s /usr/local/lib/verify-minify-json/minify_json.sh /usr/local/bin/mjson && sudo ln -s /usr/local/lib/verify-minify-json/verify_json.sh /usr/local/bin/vjson && echo "\nUse commands vjson, mjson and mjsoni to verify (CLI) and minify (CLI and CLI interactive)."
```

---

### *Uninstall*

```bash
sudo rm -rf /usr/local/lib/verify-minify-json /usr/local/bin/[vm]json*
```

---

### *Update*

```bash
sudo rm -rf /usr/local/lib/verify-minify-json && sudo git clone --depth 1 https://github.com/tomasfn87/verify-minify-json /usr/local/lib/verify-minify-json && sudo rm -rf /usr/local/lib/verify-minify-json/{.git,README.md,sample*} && echo "\nvjson, mjson and mjsoni were updated to the latest version."
```

---

<br><br>

## 1) verify_json.sh
  * receives one argument via CLI: a JSON file path, and checks if file extension is '.json'; if true, verifies if the content is valid JSON data

#### Sample CLI usage:

```bash
vjson /home/user/json_files/sample.json
```

---
## 2) minify_json.sh
  * receives two arguments via CLI: a source JSON file path and a target JSON file path
  * checks if the source file is a valid JSON file
  * removes spaces, tabs and line escapes outside of strings to reduce overall file size
  * doesn't allow the overwriting of the source file, but allows the overwriting of the target file without prompting
  * checks if the output JSON file is valid
  * if there's an error, the script is simply finished and the user must edit the command before trying again


#### Sample CLI usage:

```bash
mjson /home/user/json_files/sample.json /home/user/json_files/sample.min.json
```

---
## 3) minify_json_interactive.sh
  * does basically the same thing as 2), but in an interactive manner; no arguments are received via CLI: the script simply runs and all the necessary data must be typed step-by-step
  * it the target file already exists, the user is asked if it should be overwritten; if answer is No, it will prompt for a new file name, and won't allow the file to be saved in the same folder, asking the user to either rename it or save it to another folder
  * if there's an error, the script warns the user and prompts for a correct option until one is provided
  * use 'CTRL + C' (keyboard interrupt) to leave the script or 'CTRL + Z' to minimize it (return to background process with 'fg')


#### Sample CLI usage:

```bash
mjsoni
```
