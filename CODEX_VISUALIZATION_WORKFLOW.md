# Building and Publishing a Visualization with Codex

Codex can help turn a mathematical idea into a small interactive website. The most effective workflow is collaborative: describe the mathematical goal, ask Codex to plan with you, inspect the result in a browser, and guide revisions with concrete observations.

This guide assumes that you have a Git repository open as a workspace and want to create an interactive visualization. The workspace can be opened in **VS Code**, with Codex available from the Codex extension or panel, or in another Codex workspace interface. The essential requirement is that Codex can see and edit the files in the repository.

## 1. Start a new project in the workspace

Open the repository folder in VS Code (or another Codex workspace interface), open Codex, and start talking to it. You do not need to create files or decide the folder structure first. Tell Codex what you want to make and ask it to inspect the workspace before it begins.

For example:

> **For example—you can say this in your own words:** “I want to create an interactive visualization of `[topic]`. Take a look at my workspace and help me decide where to put the project and how we might begin. Let us talk about it before you start building.”

Codex might suggest a descriptive location such as `projects/my-visualization/`. You can accept that suggestion or ask for a different name. Once you agree, tell Codex to create the project there without committing anything:

> **For example—you can say this in your own words:** “Let us try the version we discussed. Create it in the project folder you suggested, and let me preview it before we commit anything.”

Specifying the folder keeps the work contained. Waiting to commit gives you time to review the result first.

## 2. Develop the idea through conversation

You do not need a complete design before beginning. Start with whatever you know: a topic, a rough picture, a classroom problem, or an interaction you would like to try. Codex can ask questions, propose possibilities, and build small experiments that help you decide what the visualization should become.

For example:

> **For example—you can say this in your own words:** “I have a rough idea for a visualization of `[topic]`. I would like students to notice or explore `[idea]`, but I am not sure how it should work. Can we talk through some possibilities and try a small experiment?”

The conversation may clarify questions such as:

- the mathematical meaning of each visual object;
- the controls and interactions;
- what changes when a user acts;
- what should remain fixed;
- what would be useful to try first.

You do not have to settle all of these questions before coding. A rough prototype can be part of the conversation. Once you can see it, you may change the mathematical emphasis, discard an interaction, or take the project in a different direction. Treat every plan as a temporary hypothesis.

## 3. Build something small enough to react to

For this first project, the goal is to get a **visual** into the browser as soon as possible. It can be incomplete, but it should show the main mathematical object or relationship rather than only presenting text about it.

As soon as one direction seems worth trying, ask Codex to make a small working visual:

> **For example—you can say this in your own words:** “Please make a small visual version of the idea we just discussed. It does not need to be finished; I want something we can look at and respond to. Do not commit it yet.”

The first version is an experiment, not a finished product. Its purpose is to give you and Codex something concrete to discuss.

When Codex says the first version is ready, ask it to help you see the result:

> **For example—you can say this in your own words:** “Help me open the visualization in a browser from VS Code. If the first link does not work, help me figure out what to try next.”

**In VS Code, try:**

1. Press **Ctrl+Shift+P** to open the Command Palette.
2. Run **Browser: Open Integrated Browser**.
3. Enter the preview address Codex gave you, such as `http://localhost:8000`.

How the preview opens may vary. If the first suggestion does not work, tell Codex exactly what happened and ask what to try next.

> **If you are using GitHub Codespaces, you can simply say:** “Help me open the visualization.” If the first instructions do not work, tell Codex what you see and ask what to try next.

## 4. Look, talk, revise, repeat

This is the central workflow: **look at the visualization, tell Codex what you notice, ask for a change, and look again**. Codex edits the project; your job is to guide the experiment by reacting to what you see. You can repeat this conversation as many times as needed, changing your mind or trying a different direction along the way.

Try the preview as a student would. Check more than appearance:

- Is the mathematical picture accurate?
- Is it obvious what can be clicked, dragged, or entered?
- Does each control produce the expected change?
- Can the important controls and visualization be seen together?
- Does explanatory text distinguish a mathematical object from a visual aid?
- Does the layout work at ordinary laptop width without excessive scrolling?

You do not need to know how to write the code or use a special prompt. Describe what you see, what you expected, and anything that should stay unchanged:

> **For example—you can say this in your own words:** “In the preview, `[what I observe]`. I expected `[desired behavior]`. Can you change that while keeping `[what already works]`?”

> **Example feedback, in your own words:** “The same curve has different colors in the two diagrams. Can you use one color in both?”

> **Example feedback, in your own words:** “The controls scroll out of view on my laptop. Can you keep the visualization visible while I read the explanation?”

After Codex makes a change, **refresh the preview page** to see the new version, then look again and react. If the page still does not appear to change, simply tell Codex what you are seeing and ask for help.

## 5. Review and commit the finished project

When the page behaves correctly, ask Codex to verify exactly what will be committed:

> **For example—you can say this in your own words:** “Please check that the visualization works and show me exactly which files would be included in a commit. Do not commit yet.”

Review the summary and preview one final time. Then authorize a focused commit:

> **For example—you can say this in your own words:** “Commit only the visualization project with a short, descriptive message. Leave unrelated files alone, and do not push yet.”

Finally, specify the exact destination before pushing:

> **For example—you can say this in your own words:** “Push that commit to the `main` branch of `https://github.com/USERNAME/REPOSITORY`.”

Codex should report the commit identifier, push result, and any files that remain uncommitted.

Never commit passwords, API keys, private data, or environment files. Remember that deleted secrets can remain visible in Git history.

## 6. Publish the visualization with GitHub Pages

GitHub Pages needs to be enabled only **once for each repository**.

### The first time you publish from the repository

For a public repository:

1. Open the repository on GitHub.
2. Go to **Settings → Pages**.
3. Under the branch publishing controls, select `main`.
4. Select `/(root)` as the folder.
5. Click **Save**.
6. Wait a few minutes, then refresh **Settings → Pages**. GitHub will show the public website link when it is ready.

If the repository is named `REPOSITORY`, a project stored at `projects/my-visualization` will normally appear at:

```text
https://USERNAME.github.io/REPOSITORY/projects/my-visualization/
```

### After GitHub Pages is enabled

You do not need to repeat the setup above. Whenever you commit new changes and push them to `main`, GitHub updates the website at the same public address. Wait a few minutes, then refresh the public page to see the new version.

> **For example—you can say this in your own words:** “Push my latest commit to `main`, then help me check that the public GitHub Pages site has updated.”

If the public page does not look right, tell Codex what you see and ask it to help fix the publication.

GitHub Pages sites are public. Before enabling Pages, verify that the repository and its history contain nothing sensitive. For a repository with unrelated material, consider deploying only the visualization with a GitHub Actions workflow or placing it in its own public repository.

See [GitHub's documentation on configuring a Pages publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Returning to the project later

You do not need the original conversation to continue working. The project is stored in a Git **repository**, and its **commit history** records the checkpoints you previously saved. Open the repository in VS Code, open Codex, and say that you want to continue.

> **For example—you can say this in your own words:** “I want to continue working on my `[topic]` visualization. Please find the project, run `git status`, and summarize where we left off before changing anything.”

These are the main Git terms to know:

- **Clone** means make a local copy of a repository from GitHub.
- **Pull** means bring the newest committed changes from GitHub into that copy.
- **Status** shows which local files have changed since the last commit.
- **Commit** means save your current changes in Git with a short message describing them.
- **Push** means send your local commits to GitHub.

On a different computer or in a new Codespace, you may need to **clone** the repository. If the repository is already present, ask Codex to check its **status** and **pull** the latest changes before you continue. Codex should tell you before pulling if local work might conflict with GitHub.

> **For example—you can say this in your own words:** “Make sure this is the right repository, check `git status`, and pull the latest version from GitHub if it is safe. Tell me before doing anything that might overwrite local work.”

Next, ask Codex to reopen the preview. Then return to the same central workflow: look at the visualization, describe what you notice, ask for a change, and look again.

> **For example—you can say this in your own words:** “Help me open the visualization again so we can keep working on it.”

When you finish the new round of work, ask Codex to show you the **status** and review the changed files. Then ask it to **commit** the project and **push** that commit to the correct GitHub repository. Each commit creates another useful stopping point that you can return to later.

> **For example—you can say this in your own words:** “Show me what changed. Then commit only this project and push the commit to the `main` branch of `[repository URL]`.”
