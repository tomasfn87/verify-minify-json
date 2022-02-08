# verify-minify-json

Tools to verify and minify JSON files

---
# 1) verify_json.sh
  * receives one argument via CLI: a JSON file path, and checks if file extension is '.json'; if true, verifies if the content is valid JSON data

---
  * Example: <strong>./verify_json.sh sample.json</strong>

---
# 2) minify_json.sh
  * receives two arguments via CLI: a source JSON file path and a target JSON file path
  * checks if the source file is a valid JSON file
  * removes spaces, tabs and line escapes outside of strings to reduce overall file size
  * doesn't allow the overwriting of the source file, but allows the overwriting of the target file without prompting
  * checks if the output JSON file is valid
  * if there's an error, the script is simply finished and the user must edit the command before trying again

---
  * Example: <strong>./minify_json.sh sample.json sample.min.json</strong>

---
# 3) minify_json_interactive.sh
  * does basically the same thing as 2), but in an interactive manner; no arguments are received via CLI: the script is simply run and all the necessary data must be typed step-by-step
  * it the target file already exists, the user is asked if it should be overwritten; if answer is No, it will prompt for a new file name, and won't allow the file to be saved in the same folder, asking the user to either rename it or save it to another folder
  * if there's an error, the script warns the user and prompts for a correct answer until a it's received
  * use 'CTRL + C' (keyboard interrupt) to leave the script or 'CTRL + Z' to minimize it (return to background process with 'fg')

---
  * Example: <strong>./minify_json_interactive.sh</strong>

---