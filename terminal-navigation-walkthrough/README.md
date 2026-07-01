# Lab: Terminal Navigation Walkthrough

## Objective

Demonstrate that you can use the terminal inside Codex to navigate the filesystem, create folders and files, inspect visible and hidden names, use common path shortcuts, recall commands, save simple command output into a file, and document what you learned in a short reflection file.

## Success Criteria

You have successfully completed this lab when you can:

- Create or select a dedicated Codex project folder for this lab.
- Open the terminal tab inside Codex.
- Explain that `~` refers to your home folder.
- Use terminal commands to identify your current folder.
- Use terminal commands to list visible files and folders.
- Show hidden files and folders when you choose to.
- Explain that names beginning with `.` are hidden from ordinary listings, but are not secret or protected.
- Create folders from the terminal.
- Create empty files from the terminal.
- Move into a folder from the terminal.
- Move up to a parent folder from the terminal.
- Explain the difference between an absolute path and a relative path.
- Explain what `.` and `..` mean in a path.
- Use Tab completion to finish a file or folder name.
- Use the up arrow or command history to recall a previous command.
- Search your command history for a previous command.
- Redirect simple command output into a file.
- Create a `reflection.md` file that answers the required reflection prompts.
- Explain why checking where you are before creating files or folders matters.
- Create a ZIP file of your completed lab directory and submit it with your lab submission.

## Instructions

1. Open Codex.

2. Create a new Codex project for this lab.

When Codex asks you to choose a folder, create or select this lab folder inside your course `labs` folder:

```text
~/labs/terminal-navigation-walkthrough
```

If your `labs` folder does not exist yet, create it when choosing the project folder. The goal is for this lab project to live at:

```text
labs/terminal-navigation-walkthrough
```

3. In Codex, click the terminal tab to open the project terminal.

The rest of this lab uses the terminal inside Codex. Do not ask Codex to do the commands for you. Type the commands yourself in the terminal tab.

4. Show your current location:

```sh
pwd
```

Your path should end with:

```text
labs/terminal-navigation-walkthrough
```

If it does not, move into the correct folder before continuing. For example:

```sh
cd ~/labs/terminal-navigation-walkthrough
pwd
```

Before continuing, explain what `~` means and why this path points to your lab folder inside your home folder.

5. Show what is currently inside your lab folder:

```sh
ls
```

It is okay if the folder is empty at first.

6. Create a practice folder named `terminal-practice`.

7. Show the contents of your lab folder again and verify that `terminal-practice` exists.

8. Move into the `terminal-practice` folder.

9. Show your current location and confirm that you are inside `terminal-practice`.

10. Write down or say out loud whether the path you see is an absolute path or a relative path. Explain how you can tell.

11. Create two visible folders named `notes` and `experiments`.

12. Create three visible files with different names. At least one file name should include the word `name`.

13. Show the ordinary listing for your current folder and verify that the visible folders and files appear.

14. Show the long-format listing for your current folder. Notice how it gives more detail than the ordinary listing.

15. Create one hidden-example folder named `.hidden-example` and one hidden-example file whose name starts with `.`.

16. Show the ordinary folder listing and notice whether your dot-prefixed folder and file appear.

17. Show all files and folders, including hidden ones. Confirm that your dot-prefixed folder and file appear in this listing.

18. Show all files and folders in long format. Compare this with the ordinary listing and explain what changed.

19. Move into `notes`, show your current location, then move back up to `terminal-practice` and show your current location again.

20. Explain what `.` means as a path and what `..` means as a path. Use your current location and parent folder as the example.

21. Use Tab completion to help type the name of one folder or file you created. Explain what happened when you pressed Tab.

22. Use the up arrow to recall a previous command. Before pressing Enter, read the recalled command and explain what it would do.

23. Search your command history for a command you used in this lab. Choose a search term that makes sense for a command you actually ran.

24. Save the output of a simple location or listing command into a file named `lab-location.txt` or `lab-files.txt`.

25. Show the contents of the file you created in the previous step and confirm that the command output was saved.

26. Return to the main `terminal-navigation-walkthrough` lab directory and show your current location. Your current path should end with `terminal-navigation-walkthrough`.

27. Create a file named `reflection.md` in the main `terminal-navigation-walkthrough` lab directory. You may create it from the Codex file pane/editor or from the terminal.

In `reflection.md`, answer these questions in your own words:

- Where is your `labs` folder?
- What does `~` mean?
- What is the difference between `.` and `..`?
- What is one absolute path from your lab?
- What is one relative path from your lab?
- What did your hidden file or hidden folder demonstrate?
- What command output did you redirect into a file?
- Why is guessing in the terminal risky?

28. Show the contents of `reflection.md` and confirm that your answers are saved.

## Required Deliverables

Submit a short video demonstration showing Codex and explaining:

- Your Codex project folder for this lab.
- How you opened the terminal tab inside Codex.
- Where your `labs` parent folder is.
- Where your `terminal-navigation-walkthrough` lab folder is.
- What `~` means.
- Which commands you chose for each task.
- How you verified that your folders and files were created.
- How ordinary listings and hidden-file listings are different.
- What your dot-prefixed folder and file demonstrate.
- How moving into `notes` and moving back up are different.
- What absolute and relative paths mean.
- What `.` and `..` mean.
- How Tab completion helped you.
- How you searched your command history.
- Which command output you redirected into a file and how you verified the file contents.
- How you created and checked `reflection.md`.
- Why guessing in the terminal is risky.

Also submit a ZIP file of your completed lab directory. Your ZIP file should include your created folders, visible files, dot-prefixed hidden examples, redirected-output file, and `reflection.md`.

## Submit Your Lab Directory as a ZIP File

Before you submit, make sure your completed lab directory is named:

```text
terminal-navigation-walkthrough
```

The ZIP file you submit should be named:

```text
terminal-navigation-walkthrough.zip
```

### Mac Terminal Instructions

In the Codex terminal or macOS Terminal, run:

```sh
cd ~/labs
zip -r terminal-navigation-walkthrough.zip terminal-navigation-walkthrough
```

Then submit the new `terminal-navigation-walkthrough.zip` file.

### Windows WSL Terminal Instructions

In your WSL terminal, run:

```sh
cd ~/labs
zip -r terminal-navigation-walkthrough.zip terminal-navigation-walkthrough
```

Then submit the new `terminal-navigation-walkthrough.zip` file.
