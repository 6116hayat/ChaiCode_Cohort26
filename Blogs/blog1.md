![CoverImage](./BlogResources/Blog1Cover.jpg)

<h1 align="center"> Why Version Control Exists: The Pendrive Problem </h1>

[Blog Link](https://dev.to/6116hayat/why-version-control-exists-the-pendrive-problem-5aa3)

## INTRODUCTION:

(aka: When developers lived in the fear)

![Stressed Developer](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/aua16saavfw1ct7hgpqv.jpg)

There was a time when developers didn’t fear bugs.
They feared saving files

Every save could overwrite someone else’s work. Every change came with a silent question ”_What if this breaks everything?_”

There was no rewind button, no safety net — just hope, backups named `final_final` & crossed fingers

This is the story of that world — and why version control had to exist.

---

## 🌍 The World Before Git:

Before version control systems, software development had a very physical workflow.

Code didn’t just sit in one place. It traveled

On pendrives. In emails. Through shared folders and servers (FTP). And every trip carried risk.

At its core, version control exists because multiple people needed to work on the same code base but without destroying each other’s work. That feels less of a hectic task today. But back then, teams treated code like any other regular file.

### The Pendrive Analogy:

![How code collaboration worked before version control.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/oid7mtx5dfmgnnv30un0.jpg)

Picture a group of developers working together on one big project. They all share code to each using a single **PENDRIVE.**

Yes, a single pendrive and with each and every member of the team. (Yes, even the new interns)

- Developer A updates the code and passes it along
- Developer B makes changes, overwriting A’s work.
- Developer C edit an older copy

By the time the pendrive the come back, nobody knows which version is the latest — or if any of them even run.

**Problems Faced**

- who changed what
- which version is correct
- where was the bug introduced
- is intern also adding code into this…

As projects grew, pendrives were replaced by emails. Emails were replaced by FTP servers. FTP servers were replaced by shared folders
But the core issue stayed the same: **files moved, history didn’t**

Developers tried to protect themselves the only way they knew how—by duplicating folders.

Folders began multiplying:

- `project_final`
- `project_final_v2`
- `project_latest`
- `project_latest_final`
- `project_latest_final_please_work`

![File Names in Folder](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/otkjjslw8jnx3j63g6r2.jpg)

Collaboration was fragile. One wrong move could erase hours — or even days — of effort.

This wasn’t a thought experiment or poor planning.

This was the **best** system available. And it worked — until projects grew, teams expanded, and mistakes became expensive.

---

## ⚠️ Why Git Was Created

The tipping point was **LINUX**

Linux wasn’t just another project — it was a global effort, it was huge. Thousands of developers around the world were contributing to the same code base. Managing changes at that scale pushed existing version control systems to their limits.

Since 2002, Linux relied on a proprietary tool called BitKeeper. It worked well — until it’s free license for Linux revoked in 2005. Suddenly, the Linux community had no tool that could handle the scale, speed, and distributed nature of its development.

Things didn’t just slow down.

They **broke** — and there was no backup plan.

So, Linus Torvalds did what most people do under pressure he built his own tool.

In 2005, Git was born with very specific goals:

- Never lose code — every change mattered
- Handle massive projects — scale was non-negotiable
- work fast — speed was essential, not optimal
- support distributed teams — no single point of failure

Git wasn’t designed to be friendly

It was designed to be **reliable under pressure.**

---

## ✅ Problems Git Solved

![Difference Git created](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/56304t0uskj8v7tcoay4.jpg)

Problems developers had accepted as “normal” quietly disappeared:

- Lost code became **recoverable**
- Conflicting changes became **manageable**
- Collaboration became **predictable**
- History became **permanent and searchable**

Version control stopped being a workaround and became the foundation of modern development.

---

## 🌱 The World After Git

Git didn’t just changed the tools — it changed the mindset.

For the first time in history, every change had a history. Developers could experiment freely using branches. They could collaborate without stepping on each other’s work. Mistakes weren’t disasters — they were reversible lessons.

**The ripple effect of Git were huge:**

→ Teams stopped being the afraid of change

→ Open-source projects flourished

→ Side projects felt manageable

→ Software development became more confident, more collaborative & surprisingly calmer.

Git didn’t make developers perfect.

It made failure safe.

---

## 🔍 Git vs GitHub

![Git and GitHub](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/36w8mrpmjhc7bn5yn3qv.jpg)

One final confusion remains

⇒ **Git is a tool**

- lives on our machine
- tracks changes, manages history & works offline too

⇒ **GitHub is a platform**

- simply hosts Git repositories and adds collaboration features
- works online and socially

Git existed first. GitHub made it popular.

---

### 🧠 Closing Thought

Git wasn’t created because developers wanted something new.

It was created because old ways are no longer survivable

Over time, platforms grew around Git to support collaboration. GitHub became the most widely used, but it’s not the only option. Alternatives like **GitLab, Bitbucket, SourceForge, AWS CodeCommit, and Perforce** also exist, each with its own strengths.

Still, GitHub became the place where most developers share, collaborate, and build in public.

In next post, we’ll dive into Git Basics and Essential Commands.

---
