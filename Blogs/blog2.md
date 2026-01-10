![CoverImage]()

<h1 align="center"> Git for Beginners: Basics and Essential Commands </h1>

### 🎙️<u>Introduction</u>

We’re back with another blog — with our recent star of tech world: **Git ⭐.**

Let me start with my own story a bit, while starting out my coding journey. I initially leaned toward Game-Dev. And I used to watch tutorials of the C language, learn its concepts and apply on projects.

At some point I even copy pasted the code shown in YouTube videos, comma-to-comma. But still ended with some bugs and errors. I didn’t know about Git back then.

I saved code locally, created multiple folders, and copied the same code again and again just to avoid breaking the working version.

The fog cleared up, I stopped copy-pasting tutorial code, worked on basics, understood Game-Dev isn’t for me, and learned about Git.

So I am here to speak my thoughts about Git. Let me explain more:

---

### 🐈 <u> What is Git? </u>

> **Basic Idea**: _Git is a system that tracks changes in code over time._

⇒ Things Git performs:

- A time machine for our code
- A memory management for project
- A safety net that lets us experiment without fear.

_(Simple Example: A strict mom but for code. )_

⇒ <u> Git vs GitHub: </u>

→ Git is a tool, lives on your machine, works offline

→ GitHub is a platform, that provides collaboration, social connection with developers, works online

When a group of developers, in old times use to contribute to the same codebase, they used pendrive analogy, FTP and many other stuff.

(_Hey, You don’t know Pendrive Analogy, are you the same guy from my previous blog 🤔. If not, go checkout my previous blog:_

[Blog 1: Why version Control Exists: The Pendrive Problem](https://dev.to/6116hayat/why-version-control-exists-the-pendrive-problem-5aa3) )

Think of it like Google Docs history, but for entire project — files, folders, everything.

> Git doesn’t just save files.
>
> It takes snapshots of changes over time.

- You mess up? → Go back.
- Something worked yesterday? → Prove it.
- Want to experiment? → Do it safely.

Imagine it like a rewind button, a log book, and a sandbox — all in one into our coding workflow.

---

### 🚀 <u> Why is Git is Used? </u>

As humans we make mistakes

Let’s admit, Developers are not perfect. Everyone working on same project tends to make a mistake intentionally or unintentionally.

-> Without Git:

- Developers may break the code
- Forget what they changed (unless, they are writing all changes in a notebook)
- Work with other humans (collaborative humans)
- Say “It worked yesterday” way too often

-> With Git:

- Everyone has their own of project (called a repository)
- Mistakes are not permanent and can be undone without losing progress.
- Changes are tracked and merged intelligently
- Experimentation is allowed, which provides new way of working

( Personally, I believe we living in the post Git era is a bliss. Thank you Linus Torvalds, for making our code management easy)

Git gives developers an unseen confidence — a backbone of modern software development.

---

### 🧩 <u> Git Basics and Commands </u>

![Git-Diagram](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9s9ykhvcmrlibtw5ryv2.jpg)

(This is the main ingredient of this Blog, I assume that is why you are here)

Let’s breakdown the key concepts of Git in beginner-friendly terms:

1. Repository (Repo)

   - Most used Git term, among developers
   - Home-ground for all the code files, folders, resources
   - This is where Git stores all the files and their history
   - It contains `.git` folder = Git’s brain

2. Working Directory:

   - This is the active repo, where you actively saving/pushing code files & folders.
   - This directory contains the files you actively edit before Git tracks them.

3. Staging Area:

   - Before actually pushing the code, we get to see what files or folders will get pushed.
   - Think of it like a snapshot before actually changes in GitHub repo.

4. Commit:

   - A snapshot of your project at specific moment.
   - Think of it like “saving point” in a game, to respawn later and continue
   - Comes with a message (future-you-says thanks)

   (Believe when I say to type a message before any commit, because later you’ll forget what you changed. Make you commit messages meaningful)

5. Branch:

   - A parallel timeline for your code.
   - You can experiment your coder instinct here without disturbing the main timeline.

   (Imagine it like a clone of yourself, respawned in alternate universe same as yours. Now you can do things with that clone too.)

6. Head:

   - Your current position in the codebase.
     (Git’s way of saying “this is where you are right now”)
   - Simple way: A pointer to current commit.

   (If you don’t understand, it’s fine. Git sorts this task for you)

---

### 🛠️ <u> Common Git Commands </u>

Let’s walkthrough a simple workflow as if you’re starting fresh:

(Before anything, Open a folder in VS Code, navigate to cmd terminal and perform these commands)

You can create files using your IDE or terminal — both work.

⇒ Git WorkFlow:

1. Create a Folder

   ```cmd
   mkdir your-project-name
   cd your-project-name
   ```

   - `mkdir` : stands for make directory
   - `cd` : stands for change directory
   - Above command changes your directory and change to the current one. ( In our case, new project created)

2. Initialize Git:

   ![Git-Init](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nsezqh5zsclb94z0v32n.png)

   ```cmd
   git init
   ```

   - `init` : stands for initialization.
   - Above commands means, we want to initialize a `.git` folder in the current project directory.
   - Simply, set up s hidden .git directory to manage and store the changes

3. Create File:

   ![Git_echo](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hz3c6yyousrchkxfq81e.png)

   ```cmd
   echo "Hello Git" > hello.txt
   ```

   - `echo` : a command which is used to print the text to output tab
   - `>` : this simple greater than sign means to shift the content `“Hello Git”` to the hello.txt file
   - Above command means to write “Hello Git” to a file called hello.txt in the directory.
     (If a file hello.txt is not present, it creates one for us)
   - You can change the file name, or the content under “ “ according to your needs.

   ![Git-echo2](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/v3q2v4eq5j36nynmoap6.png)

   ```cmd
   echo "Another Line" >> hello.txt
   ```

   - `>>` : two greater than means we don't want to overwrite previous content instead, we want to add another line.
   - Above command means to write another text line `(Another line)` in the **hello.txt** file.

4. Check Status:

   ![Git-Status](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/4g2qk971nm5c42d5loe7.png)

   ```cmd
   git status
   ```

   - Above command means to show us which files are new, modified, staged
   - At this point, **hello.txt** will appear an untracked file

5. Stage Changes:

   ![Git-Add](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/96kmoc2b299wlq3qix9r.png)

   ```cmd
   git add hello.txt
   ```

   - Above command moves file into staging area, preparing to commit.
   - You can stage multiple files or use `git add .` to stage everything.

   #### <u> Git Ignore </u>

   Hey readers!! If you are so far here I would like to add more to your journey.

   Sometimes you’ll have files in your project that you **don’t want the Git to track** — like temporary files, logs or sensitive config files. To handle this, we use a special file called `.gitignore`

   Let’s back to the topic now.

6. Commit changes:

   ![Git-commit](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/v77yp1hvd8c12sq9i2y6.png)

   ```cmd
   git commit -m "First commit: Add hello.txt"
   ```

   - `commit` : saves changes to your local repository.
   - `-m` : stands for messages
   - Above command means, save staged changes in repository hstory with the message you gave (In our case, `"First Commit: Add hello.txt"`)

#### Summary:

1. Folder creating → `mkdir` / Editor
2. Initialize repository → `git init`
3. Add Files → `echo` / Editor
4. Check status → `git status`
5. Stage Changes → `git add`
6. Commit → `git commit -m “your-message”`

### Other Powerful Commands:

These commands comes in handy, being a developer I have used a lot. If you are dev too, you know them too.

1. Coding logs:

   ![Git-Log1](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/qd5hn665nl53zat0xxk6.png)

   ![Git-Log2](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/geyg5n8lcx2hrs2nvan4.png)

   ```cmd
   git log
   ```

   - Shows up your code history with an ID, author, author-email, date and message.
   - Reading commits like timeline
     (I would say flipping through a coding diary)

2. Commit difference:

   ![Git-Diff](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rtp3dorb007r8byjs9z7.png)

   ```cmd
   git diff
   ```

   - `diff`: stands for difference
   - Shows changes you've made in files but haven't added it. You'll see the line differences.

     - `-` (minus) → content removed
     - `+` (plus) → content added

   - Works before `git add` . If you run it after staging, it returns nothing because changes are already in staging area.

   ![Git-CommitDiff](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/etefx7fcpo8hp9fhvcbk.png)

   ```cmd
   git diff commit1 commit2
   ```

   - You can also use the ID of your selected commits, to see the difference between them.

3. Branches:

   ![Git-Branch](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7o7ymjosy7ck503fe99k.png)

   Creating Branch

   ```cmd
   git branch your-branch-name
   ```

   - creates a new branch with name you have given

   Branch List

   ```cmd
   git branch
   ```

   - shows all the git branch list, connected to your current repository.

   Change Branch

   ```cmd
   git checkout branch-name
   ```

   - shifts the branch from the current one, to the mentioned one

By the end, you’ve not only built your project—you’ve built a history of your project.

---

### 😅 <u>Common Beginners Mistake: </u>

Learning about isn’t about perfection — it’s about making mistakes and realizing they’re part of the journey.

Basic Mistakes every beginner bumps into:

→ Forgetting to commit:

Every changes needs to be mentioned and stored in history. One last avoidance of procastination may lead you a good commit timeline.

→ Committing everything blindly:

Running `git add .` and committing without checking what’s inside leads you to a loop of debug logs and secret configs in repo.
(Even we check the person, before committing to marry him/her. Why not your CODE!!)

→ Writing bad commit messages:

Fix stuff” or “Update code” doesn’t help future you (or teammates). A good commit message is like a diary entry—it tells the story of what changed.

→ Being afraid of Git errors:

Seeing “detached HEAD” or “merge conflict” feels terrifying at first. But Git errors aren’t disasters—they’re just puzzles waiting to be solved.

> Everyone breaks Git once.
>
> The pros just know how to fix it.

---

At last,

> This is the end.
>
> Hold your commits and count to ten
>
> Feel the Git moving, and then
>
> Remember your commit message again
>
> ~ Hayat (Original)

Now, you have covered so much of the Git basics — now it’s time for you to get moving and put your laptop to work.

- **Practice locally** → Start small, experiment freely, and let Git become second nature.
- **Break things on purpose** → Mess up boldly—fixing mistakes is the fastest way to learn.
- **Learn branches next** → Branches are your playground for safe experiments.
- **Explore GitHub after mastering basics** → Share your work online and step into real collaboration.

We’ll meet again in the next blog, where we go under the hood of `.git`.

---
