# Lab: JSON for a Personal AI Assistant

## Objective

Create, validate, format, inspect, intentionally break, fix, and explain JSON data for a simple personal AI assistant.

Modern software systems use JSON to exchange structured information. APIs return JSON. AI tools often accept JSON arguments. Apps use JSON to save settings, describe users, represent objects, and communicate between systems.

## Success Criteria

You have successfully completed this lab when you can:

- Create a dedicated lab project folder inside your `labs` parent folder.
- Open the Codex terminal panel and launch Zed from the project folder with `zed .`.
- Verify that `jq` is installed, or install it for your operating system.
- Write valid JSON by hand.
- Use strings, numbers, booleans, arrays, and nested objects.
- Validate JSON from the command line with `jq`.
- Use `jq` to pretty-print messy JSON.
- Use `jq` to compact JSON.
- Use `jq` to inspect and extract specific values.
- Save generated JSON output into new files with `>`.
- Explain what your JSON structures represent.
- Spot and fix common JSON mistakes.
- Create an `answers.md` file with your checkpoint responses.
- Turn your lab directory into a public GitHub repository and submit its URL.

## Instructions

1. Open Codex.

2. Create a new Codex project for this lab.

When Codex asks you to choose a folder, create or select this lab folder inside your course `labs` folder:

```text
~/labs/personal-assistant-json
```

If your `labs` folder does not exist yet, create it when choosing the project folder. The goal is for this lab project to live at:

```text
labs/personal-assistant-json
```

3. In Codex, click the terminal button in the upper right. The terminal should open in the lower window.

For the rest of this lab, run terminal commands from inside this `personal-assistant-json` project folder unless a step explicitly says otherwise.

4. Check whether `jq` is installed:

```sh
jq --version
```

If that prints a version number, you are ready. Some Macs already include `jq`, so always check before installing anything.

If `jq` is not installed, install it with Homebrew if on a Mac:

```sh
brew install jq
```

If on Windows in wsl enter:
```
sudo apt update
sudo apt install jq
```

Then check again:

```sh
jq --version
```

5. Launch Zed and open the `personal-assistant-json` folder.

6. Create a file named `answers.md` in Zed. Use this file for all checkpoint answers.

Open or create `answers.md` in Zed. If the file is not visible yet, create it from Zed's file tree or file menu.

7. Create a file named `assistant-profile.json` in Zed.

Open or create `assistant-profile.json` in Zed. If the file is not visible yet, create it from Zed's file tree or file menu.

8. In `assistant-profile.json`, write a JSON object that describes a student using a personal AI assistant.

Your JSON must include these fields:

- `student_name`
- `grade_level`
- `favorite_subject`
- `uses_voice_mode`
- `daily_study_minutes`

Example shape:

```json
{
  "student_name": "Ava",
  "grade_level": 10,
  "favorite_subject": "computer science",
  "uses_voice_mode": true,
  "daily_study_minutes": 45
}
```

You may use your own values. Save the file before continuing.

9. Validate `assistant-profile.json`:

```sh
jq . assistant-profile.json
```

If your JSON is valid, `jq` will print it back nicely formatted. If your JSON is invalid, `jq` will show an error. Fix your JSON until the command works.

10. In `answers.md`, answer this checkpoint:

```text
Checkpoint 1
What data type is each value in assistant-profile.json?
```

Use this style:

```text
student_name: string
grade_level: number
favorite_subject: string
uses_voice_mode: boolean
daily_study_minutes: number
```

11. Create a file named `messy.json` in Zed.

Open or create `messy.json` in Zed. If the file is not visible yet, create it from Zed's file tree or file menu.

12. Put this intentionally ugly JSON into `messy.json`:

```json
{"student_name":"Ava","grade_level":10,"favorite_subject":"computer science","uses_voice_mode":true,"daily_study_minutes":45,"favorite_tools":["calendar","weather","notes"],"preferences":{"response_style":"clear and direct","include_examples":true,"max_answer_length":"medium"}}
```

Save the file before continuing.

13. Pretty-print `messy.json` on screen:

```sh
jq . messy.json
```

14. Save a pretty-printed version into `pretty.json`:

```sh
jq . messy.json > pretty.json
```

Open or display `pretty.json` and confirm that the information did not change. Only the formatting changed.

15. In `answers.md`, answer this checkpoint:

```text
Checkpoint 2
Did jq change the meaning of the JSON?
What did jq change?
Why is pretty-printed JSON easier for humans to read?
```

16. Compact `pretty.json` on screen:

```sh
jq -c . pretty.json
```

The `-c` option means compact output.

17. Save the compact version into `compact.json`:

```sh
jq -c . pretty.json > compact.json
```

Open or display `compact.json`. Notice that it is harder for humans to read, but it is still valid JSON.

18. In `answers.md`, answer this checkpoint:

```text
Checkpoint 3
Why might an API send compact JSON instead of pretty JSON?
Is compact JSON different data, or just different formatting?
Which version would you rather debug: pretty or compact?
```

19. Go back to `assistant-profile.json` in Zed and add a field named `favorite_tools`.

The value should be a list of at least three tools your assistant might use.

Example:

```json
"favorite_tools": ["calendar", "weather", "notes"]
```

Your full JSON should still be one valid object. Save the file before continuing.

20. Validate `assistant-profile.json` again:

```sh
jq . assistant-profile.json
```

21. Query the whole array:

```sh
jq .favorite_tools assistant-profile.json
```

22. Query only the first favorite tool:

```sh
jq .favorite_tools[0] assistant-profile.json
```

23. In `answers.md`, answer this checkpoint:

```text
Checkpoint 4
What does [0] mean?
Why is the first item not [1]?
What command would show the second favorite tool?
```

24. Use `jq` to extract individual values from `assistant-profile.json`:

```sh
jq .student_name assistant-profile.json
jq .favorite_subject assistant-profile.json
jq .daily_study_minutes assistant-profile.json
jq .favorite_tools assistant-profile.json
jq .favorite_tools[0] assistant-profile.json
```

25. Print the student name as raw text:

```sh
jq -r .student_name assistant-profile.json
```

The `-r` option means raw output. It removes the JSON quotes around strings.

26. In `answers.md`, answer this checkpoint:

```text
Checkpoint 5
What is the difference between jq .student_name and jq -r .student_name?
Why might raw output be useful in a shell script?
```

27. Go back to `assistant-profile.json` in Zed and add a field named `preferences`.

The value should be an object with these fields:

- `response_style`
- `include_examples`
- `max_answer_length`

Example:

```json
"preferences": {
  "response_style": "clear and direct",
  "include_examples": true,
  "max_answer_length": "medium"
}
```

Your JSON should still be one valid object. Save the file before continuing.

28. Validate `assistant-profile.json` again:

```sh
jq . assistant-profile.json
```

29. Query nested values:

```sh
jq .preferences.response_style assistant-profile.json
jq .preferences.include_examples assistant-profile.json
jq .preferences.max_answer_length assistant-profile.json
```

30. In `answers.md`, answer this checkpoint:

```text
Checkpoint 6
What does nesting mean in JSON?
Why does .preferences.response_style need two names separated by a dot?
What command would extract only max_answer_length?
```

31. Make a copy of your valid profile file:

```sh
cp assistant-profile.json broken.json
```

32. Open `broken.json` in Zed. Create each of the following mistakes one at a time. After each mistake, run the validation command, write down what happened in `answers.md`, and fix the mistake before moving to the next one.

Validation command:

```sh
jq . broken.json
```

Mistakes to try:

- Remove a comma between two fields.
- Add a trailing comma after the final field.
- Remove the quotes around a key.
- Change `true` to `True`.
- Change one double quote to a single quote.
- Delete one closing brace.
- Change an array `[` into an object `{`.
- Remove the colon after a key.

33. In `answers.md`, answer this checkpoint:

```text
Checkpoint 7
Which mistake gave you the clearest error message?
Which mistake gave you the most confusing error message?
Why do computers reject JSON that humans can still sort of understand?
```

34. Create a new file named `robot-status.json` in Zed.

Open or create `robot-status.json` in Zed. If the file is not visible yet, create it from Zed's file tree or file menu.

35. Write valid JSON describing a robot.

Your JSON must include:

- robot id
- battery percentage
- online status
- current location
- sensor readings
- list of active tasks
- last command received

Requirements:

- Use at least one string.
- Use at least one number.
- Use at least one boolean.
- Use at least one array.
- Use at least one nested object.
- Your JSON must validate with `jq`.

36. Validate `robot-status.json`:

```sh
jq . robot-status.json
```

37. Pretty-print it into a final formatted file:

```sh
jq . robot-status.json > robot-status-pretty.json
```

38. Create a compact version:

```sh
jq -c . robot-status.json > robot-status-compact.json
```

39. In `answers.md`, answer this checkpoint:

```text
Checkpoint 8
What does your robot JSON describe?
Which fields are strings?
Which fields are numbers?
Which fields are booleans?
Where did you use an array?
Where did you use nesting?
Which file is easier to read: robot-status.json, robot-status-pretty.json, or robot-status-compact.json?
Which file looks most like what might be sent across a network?
```

40. Optional stretch: create a file named `classroom.json` in Zed that models the state of a classroom.

Your JSON should include:

- class name
- room number
- instructor
- number of students
- list of teams
- for each team: team name, members, project idea, and `needs_help`

Validate it:

```sh
jq . classroom.json
```

Extract just the teams:

```sh
jq .teams classroom.json
```

Extract the first team:

```sh
jq .teams[0] classroom.json
```

Extract the first team's project idea:

```sh
jq .teams[0].project_idea classroom.json
```

Create compact and pretty versions:

```sh
jq -c . classroom.json > classroom-compact.json
jq . classroom.json > classroom-pretty.json
```

41. Before submitting, verify your required files are present:

```sh
ls
```

Your folder should contain these required files:

```text
assistant-profile.json
answers.md
broken.json
compact.json
messy.json
pretty.json
robot-status.json
robot-status-compact.json
robot-status-pretty.json
```

Optional stretch files:

```text
classroom.json
classroom-compact.json
classroom-pretty.json
```

42. Validate the required JSON files one more time:

```sh
jq . assistant-profile.json
jq . messy.json
jq . pretty.json
jq . compact.json
jq . robot-status.json
jq . robot-status-pretty.json
jq . robot-status-compact.json
```

Do not worry if `broken.json` is not valid while you are testing errors. Before you submit, either fix `broken.json` so it is valid again or explain in `answers.md` that it was left broken on purpose.

Reference while working:

```text
{ } means object
[ ] means array
"text" means string
42 means number
true and false mean boolean
null means empty or unknown
JSON keys must use double quotes
Items are separated by commas
There is no trailing comma after the final item
```

Common `jq` patterns:

```sh
jq . file.json
jq .field_name file.json
jq .outer.inner file.json
jq .items[0] file.json
jq -r .field_name file.json
jq -c . file.json
```

## Required Deliverables

Submit a public GitHub repository URL for this lab.

Your repository should include the files you created and generated during the lab:

- `assistant-profile.json`
- `answers.md`
- `broken.json`
- `compact.json`
- `messy.json`
- `pretty.json`
- `robot-status.json`
- `robot-status-compact.json`
- `robot-status-pretty.json`
- any optional stretch files you created

Your `answers.md` file should include all checkpoint responses.

## Submit Your Lab With GitHub

Before you submit, make sure you are inside your lab directory:

```sh
pwd
```

The path should end with:

```text
labs/personal-assistant-json
```

Initialize Git, commit your work, create a public GitHub repository, and push it:

```sh
git init
git add .
git commit -m "Complete personal assistant JSON lab"
gh repo create personal-assistant-json --public --source=. --remote=origin --push
```

Get the URL for your GitHub repository:

```sh
gh repo view --web
```

Copy the GitHub repository URL from your browser and submit that URL with your lab submission.

And don't forget your video explaining what you did.
