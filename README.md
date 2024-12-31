# d2mr-assessment

Centralized directory for D2MR mini-project assessment materials.

## Setup instructions

1. Create a fork of this repository. This will create a copy of the repository in your GitHub account that you control and can modify. 
    1. Click the "Fork" button in the top right corner of this page (assuming you are viewing this on GitHub)
    2. Rename the fork by appending your CNetID: `d2mr-assessment-yourcnetid` (e.g. `d2mr-assessment-ndowling`). 
    3. Add Dr. Dowling and your section TA as collaborators to your forked repository.
2. Create an R project in RStudio and clone your forked repository to your local machine. The course website has a full guide on how to do this, but the basic steps are:
    1. In RStudio, go to File -> New Project -> Version Control -> Git
    2. Enter the URL of your forked repository (e.g. `https://github.com/nrdowling/d2mr-assessment-ndowling.git`) and click "Create Project"
    3. Because you are using a forked repository, you can pull from both your remote version of the fork or from the main "upstream" repository, but then push only to your fork, confident that you're leaving the main (public) repository untouched.
3. Periodically -- at minimum before you begin a new project -- pull changes from the main repository to your forked repository to ensure you have the most up-to-date version of the assessment materials. There are [instructions for doing this in RStudio below](#pullupstream) (it's not quite as simple as syncing with your own fork or repos).

## Completing mini-projects

Mini-projects on the menu have a corresponding directory in this repository. Each directory contains either a README.md file with general instructions for approaching the project *or* a Quarto notebook (e.g., cleaning-level-1.qmd) that will guide you through completing the more structured projects.

### Project types

Mini-projects will probably fall into one of the following categories:

### Structured activities

These projects will have a Quarto notebook that will guide you through the project, like leveled data cleaning exercises. The notebook will include instructions, code snippets, and explanations to help you complete the project. Unless otherwise stated, all aspects of the project should complete these projects in the Quarto notebook.

### Open-ended projects

These projects will have a README.md file that will provide a general description of the project and some guidance on how to approach it. If it's sensible to do so, you can put your work in that same directory, in whatever form it takes.

In some cases it's won't make sense (or even be possible) to complete the project in the directory of your centralized assessment repo. For example, mini-projects that require some kind of "publication" (like a website or Quarto APA manuscript) will need to exist in their own dedicated repositories; they can't run as sub-directories of this one. 

In those cases, you should still complete the assessment.md file in the associated project directory (here in this centralized repo!), which will include any necessary information about how to access your work. 

### Off-the-menu projects

You can also design your own "off-the-menu" projects. To do so, create a new directory in the repository, name it appropriately, and add a README.md file proposing your project. 

**The proposal file should include:**

1. Simple description of what you plan to do
2. One of the following:
    1. A list of at least 3 learning objectives the project will allow you to demonstrate
    2. A simple description (1 paragraph or bullet points) of what off-the-syllabus skills you would like to practice 
3. Brief explanation of why you want to take on this project
4. Description of what the submission will look like (dedicated repo? directory in this centralized repo? website url? interpretive dance performance?)

The goal isn't to impress me. I just want to be confident that this undertaking will be 1) doable and 2) useful. 

On Canvas, go to your next open mini-project assignment and submit a link to the README file you just created, which will alert me to review your proposal. If I give that assignment a "complete" grade, you're good to go! If I get it an "incomplete," I'll provide feedback on what needs to be changed before you can proceed.

When you submit, you'll follow the same process as the on-the-menu projects, but you'll be resubmitting to the same assignment on Canvas that you submitted your proposal to.

## Submitting mini-projects

When you finish a mini-project, you should complete the assessment.md file in the project directory, then submit a link to that directory on Canvas.

**No matter what kind of project it is (structured, open-ended, or off-the-menu), the project needs a directory here in this repo, and that directory needs to include a completed assessment.md file.**

Submit to one of your 10 mini-project assignments on Canvas (whichever the next open one is, doesn't matter as long as it's not one you've already used). The Canvas assignment is simply a text box where you should include:

1. The name of the project and/or a brief description of the project
2. A link to the directory *in this centralized repository* where you completed the project
    1. If you completed the project in a separate repository, your assessment.md file should explain how to access your work.
3. Any additional info you'd like your grader to know

Submitting to Canvas functionally serves to alert us that you've completed a project and that we should grade it. The actual assessment, including any feedback, happens in the assessment file in this repository. Your Canvas assignment will be marked as "complete" when we've finished grading your project and have pushed the assessment back to your repo. Points earned will be added to your cumulative mini-project scores in Canvas (you won't see numbers for each project, just complete/incomplete).


### Pulling from the main (upstream) repository {#pullupstream}

You should periodically pull changes from the main repository to your forked repository to ensure you have the most up-to-date version of the assessment materials. Unfortunately RStudio doesn't have a nice easy button to click for this, so you'll need to do it from the terminal pane in RStudio.

Before the first time you pull from main, you need to tell git where the main repository is. You only need to do this once. In the terminal pane in RStudio, run the following command:

```bash
git remote add upstream https://github.com/nrdowling/d2mr-assessment.git
```

Now you can pull changes from the main repository by running the following command (in the terminal):

```bash
git pull upstream main
```

You may get the following message:

```
hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint: 
hint:   git config pull.rebase false  # merge
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint: 
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.
```

If you get this message and you understand all those options, you can make up your mind about what to do next. If this is jibberish to you, just run the following command:

```bash
git config pull.rebase false
```

Now try the `git pull upstream main` again. This time it should work, but you'll get pulled into a text editor to write a commit message. You have 2 options:

1. Just close the text editor (it's probably vim) by typing `:q` and hitting enter. This is quick and dirty and not ideal, but since you know you'll never need to merge your fork back to main, it's fine in this context.
2. Write a commit message. This is the "right" way to do it, but it's a bit more complicated. If you try to just start typing, you won't see anything happen. That's because you're in "command mode" in vim. If you want to do this:
    1. Hit 'i' to enter 'i'nsert mode.
    2. Type your commit message.
    3. Hit `esc` to exit insert mode.
    4. Type `:wq` and hit enter to save and close the text editor.


Granted, both these assume your machine is using vim (or similar) as a text editor. If that doesn't work, your machine is probably using something other than vim. On PCs it's probably nano. You can try `ctrl+x` to exit, and then `y` to save changes and `enter` to confirm. Still not working? Bust out your troubleshooting workflow. Google is your friend.

Have you hit an impassable wall with pulling from the upstream repo? It's ok. This isn't a major learning objective for the class. You can also do this outside of RStudio with apps designed for git, like GitHub Desktop. I'll leave it to you to figure out how to do that.

## Mini-project assessment menu


Earn up to 40 points across all mini-projects for meeting course objectives. Some of the menu items are highly structured (like the data cleaning and wrangling), but most are very open to interpretation. Unless the mini-project has a link to a specific assignment, you should just work with the short description provided here and take it in whatever direction you like.

Do not use the same data from your independent project to complete the mini-projects unless the assignment calls for it or you receive prior approval. You can use the same data for multiple mini-projects, but you should demonstrate different skills in each.

These projects do not have strict submission or grading requirements. You can make any mini-project as simple or as complex as you like. If you write a `hello_world()` function that's 5 lines long, that's fine, but you'll probably only be able to demonstrate a couple of the learning objectives. If you write a `hello_world()` function that's 50 lines long, or write multiple functions and build them into your own package, you'll probably be able to demonstrate a whole lot more than that.

Earn up to 10 points across all mini-projects for assignment engagement. That 5-line `hello_world()` function might not earn any engagement points, while the 50-line one could earn you all 10.

Some projects are marked as "off the syllabus" (OtS). These are opportunities to learn and demonstrate skills that aren't explicitly covered in the course. These will let you showcase the skills we do explicitly cover in a different context, or let you explore something that interests you.

You are welcome to go "off the menu" (OtM) to design your own mini-project that lets you focus on your interests while still demonstrating the course objectives. If you choose to do this, you should submit a proposal for approval. View the instructions for an off-the-menu proposal [here](off-the-menu-proposal.html).

Off-the-syllabus and off-the-menu projects are assessed the same as other projects. If you want, you can earn all 40 points through OtS or OtM projects. They are also a great way to earn the engagement points, as they require you to take a more active role in your learning.

Tags:

1. GC: This project should be completed through the corresponding GitHub Classrooms assignment.
2. DEMO: This is not a mini-project, but a demonstration of the skills you'll need to complete the related mini-project. There is nothing to complete, and you should not submit these for grading.
3. OtS: This project is "off-the-syllabus" because it involves skills beyond the learning objectives of the class.


### Assessed learning objectives

1.  Data cleaning
    - (GC, DEMO) Walkthrough
    1. (GC) Level 1
    2. (GC) Level 2
    3. (Pairs/groups) Un-clean some data & swap to clean
2. Data wrangling
    - (GC, DEMO) Walkthrough
    1. (GC) Level 1
    2. (GC) Level 2
    3. (Pairs/groups) Ravage some poor datasets & swap to wrangle
    4. (OtS) Access, read in, and wrangle nested or non-tabular data (e.g., JSON, XML)
3.  Data visualization & presentation
    - (GC, DEMO) Walkthrough
    1. (GC) Level 1
    2. (GC) Level 2
    3. Create a custom ggplot2 theme
    4. (Pairs/groups) Make plots (w/ some minimum requirements) & swap to recreate
    5. Create beautiful tables with packages like `kableExtra`, `flextable`, `stargazer` , `gt`, or `xtable` ([there are lots!](https://towardsdatascience.com/top-7-packages-for-making-beautiful-tables-in-r-7683d054e541))
    6. Present the same data in multiple ways (e.g., bar chart, line chart, table)
    7. (OtS) Create a plot with non-ggplot2 packages
4. Data analysis
    1. (GC) Descriptive statistics
    2. (GC) Hypothesis testing
    3. (OtS) Higher-level statistics
5. Data communication
    1. Transpose a paper into Quarto markdown
    2. Write a memo or brief report based on a previous assignment
    3. Create a demo .qmd or .Rmd for one or more class topics
    4. (OtS) Recreate your Quarto report with papaja or RMarkdown
    5. (OtS) Use Quarto to publish something other than a document (e.g., website, presentation, dashboard)
    6. (OtS) Create a `shiny` app or dashboard
6.  R Programming
    - (DEMO) `hello_world()` examples
    1. Create a `hello_world()` function
    2. Create a plotting function
    3. Create a wrangling function
    4. Recreate a function from base R or a non-tidyverse package using tidyverse functions
    5. (OtS) Create a package
7. Git & GitHub (these can use real projects or dummy data)
    1. Set up a skeleton repo to create APA quarto manuscripts
    2. (Groups) create and maintain a repo as collaborators and use cloning, forking, merging etc
    3. (OtS) Create a GitHub pages website
    4. (OtS) Host a package through a GitHub repo
8. Unassessed Learning Objectives & Miscellaneous
    1.  Create and document a style guide and apply it to a script or notebook
    2.  Create a debugging journal
    3.  Write documentation for a function that you’ve written (e.g., a `hello_world()` function or something you use in your independent project), following the standard documentation guidelines and expectations (i.e., it should match what you see when you use `?somefunction` )
    4.  In the format of your choosing (bullet points, paragraphs, mindmap, flowchart, slides, etc.), show me how you understand the points listed under “conceptual skills”.
    5.  Get obsessed with LaTeX!
    6.  Contribute answers to stackoverflow, reddit, etc.
    7.  Create a tutorial on a topic of your choosing in the format of your choosing