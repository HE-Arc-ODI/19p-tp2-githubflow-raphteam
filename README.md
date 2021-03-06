**Author**: [@PiotrBerebecki](https://github.com/PiotrBerebecki)  
**Maintainer**: [@PiotrBerebecki](https://github.com/PiotrBerebecki)

**Adapted for the ODI class at HEG Arc**: [@urosselet](https://github.com/urosselet) and @dylanmontandon


# Git Workflow Workshop for Two Programmers 💻 💻



<!-- ***********************************************************-->
## Workshop summary

An exercise to practice git workflow skills. The workshop should be undertaken by two programmers, working on two computers. The skills practiced include:

- cloning a repository
- creating branches
- switching branches
- adding changes to staging area
- committing changes
- pulling latest version from the remote master branch
- merging master branch into recently created branch
- resolving merge conflicts
- pushing to remote repository
- creating a pull request on GitHub
- merging a pull request on GitHub



<!-- ***********************************************************-->
# Initial setup :rocket:

You're working in a team of two on a project for a new client.

## Step 1 - Accept the github classroom assignment and clone the resulting repo

1. The first student to accept the assignment creates a team. The second one joins the team. Please use a combination of your first names (for example "alice_bob") for the team name.

2. [Clone](https://help.github.com/articles/cloning-a-repository/) this new repository using your terminal.

  <img src="images/clone-repository-dialog.png" width="500" height="auto" alt="clone repository dialog">

  ```sh
  $ git clone 'PASTE THE URL OF YOUR REPOSITORY HERE'
  ```

3. Move into the newly created directory.
``` sh
$ cd [yourDirectory]
```


This is what your remote and local repositories look like after this. HEAD is a reference to your current location.<br>
<img src="images/step1GitFlow.png" width="350" height="auto" alt="repo visual after step 1">

  <!-- ***********************************************************-->
   ## Step 2 - Raise your issues on the work to be done

Normally, you would decide on which "features" you were going to build and then break these down into smaller issues before starting the work.

For the sake of this exercise, we're just going to [add two issues](https://help.github.com/articles/creating-an-issue/) at the moment. Your client wants a beautifully styled heading for the homepage. It should be simple, bold, black writing with a background shadow that makes it stand out.

| Programmer A | Programmer B |
|--|--|
|1. Raise a new issue corresponding to the creation of the **html homepage**.|1. Raise a new issue corresponding to the creation of the **css stylesheet**.|
|2. In the body of the issue, provide more detail about how to complete the work: i.e. create an html file called "index.html". | 2. In the body of the issue, provide more detail about how to complete the work: i.e. create a css file called "style.css". |
|3. Assign yourself to this issue.|3. Assign yourself to this issue.|




<!-- ***********************************************************-->
## Step 3 - Create and move to a new branch

There are many types of workflow. In the ODI class, we use [the GitHub flow](https://guides.github.com/introduction/flow/), where the `master` [branch](](https://help.github.com/articles/about-branches/)) is always deployable. In this flow, each branch is used for a separate feature.

| Programmer A | Programmer B |
|--|--|
|1. Create a branch with a unique and descriptive name. For example, `create-homepage`.|1. Create a branch with a unique and descriptive name. For example, `create-stylesheet`.|
| <pre>$ git branch create-homepage</pre>| <pre>$ git branch create-stylesheet</pre>| 


<br>
<img src="images/step3(1)GitFlow.png" width="300" height="auto" alt="repo visual after step 1">

2. Leave the master branch by switching to the new branch you have just created.

| Programmer A | Programmer B |
|--|--|
| <pre> $ git checkout create-homepage </pre>| <pre> $ git checkout create-stylesheet </pre>|

<br>
<img src="images/step3(2)GitFlow.png" width="300" height="auto" alt="repo visual after step 1">

<!-- ***********************************************************-->
## Step 4a - Programmer A : Write enough HTML to satisfy the requirements

1. Add the following code into a file called `index.html`.
    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="style.css">
        <title>Git Workflow Workshop</title>
    </head>

    <body>

        <h1 class="some-heading">GIT WORKFLOW WORKSHOW</h1>

    </body>

    </html>
    ```

## Step 4b - Programmer B : Write enough CSS to satisfy the requirements


1. Create a new file called `style.css` which contains:
    ```css
    * {
      margin: 0;
      padding: 0;
    }

    .page-heading {
      box-sizing: border-box;
      font-family: "Avant Garde", Avantgarde, "Century Gothic", CenturyGothic, "AppleGothic", sans-serif;
      font-size: 3.5rem;
      padding: 5rem 3rem;
      text-align: center;
      text-rendering: optimizeLegibility;
      color: #131313;
      background-color: #e7e5e4;
      letter-spacing: .15em;
      text-shadow: 1px -1px 0 #767676, -1px 2px 1px #737272, -2px 4px 1px #767474, -3px 6px 1px #787777, -4px 8px 1px #7b7a7a, -5px 10px 1px #7f7d7d, -6px 12px 1px #828181, -7px 14px 1px #868585, -8px 16px 1px #8b8a89, -9px 18px 1px #8f8e8d, -10px 20px 1px #949392, -11px 22px 1px #999897, -12px 24px 1px #9e9c9c, -13px 26px 1px #a3a1a1, -14px 28px 1px #a8a6a6, -15px 30px 1px #adabab, -16px 32px 1px #b2b1b0, -17px 34px 1px #b7b6b5, -18px 36px 1px #bcbbba, -19px 38px 1px #c1bfbf, -20px 40px 1px #c6c4c4, -21px 42px 1px #cbc9c8, -22px 44px 1px #cfcdcd, -23px 46px 1px #d4d2d1, -24px 48px 1px #d8d6d5, -25px 50px 1px #dbdad9, -26px 52px 1px #dfdddc, -27px 54px 1px #e2e0df, -28px 56px 1px #e4e3e2;
    }
    ```



<!-- ***********************************************************-->
## Step 5 - Add the new files to the staging area

| Programmer A | Programmer B |
|--|--|
|1. Add `index.html` to the [staging area](http://softwareengineering.stackexchange.com/questions/119782/what-does-stage-mean-in-git).|1. Add `style.css` to the [staging area](http://softwareengineering.stackexchange.com/questions/119782/what-does-stage-mean-in-git).|
|<pre>  $ git add index.html </pre>|<pre>  $ git add style.css</pre>|
|<img src="images/step5GitFlowA.png" width="400" height="auto" alt="repo visual after step 1"> |<img src="images/step5GitFlowB.png" width="400" height="auto" alt="repo visual after step 1">|

<!-- ***********************************************************-->
## Step 6 - Commit your changes

The history of a project is made up of ["commits"](http://stackoverflow.com/questions/27˜Ω45076/what-are-the-differences-between-git-commit-and-git-push). Each commit is a snapshot of your whole repository at one particular time.

1. Commit the files that are in the staging area.

  Before closing the commit message with a quote symbol you can press enter on your keyboard to continue typing in the new terminal line. The text in the second line can be used as an additional message.

  It is a good practice to link your commit to an existing issue by typing  `Relates #1`. Thanks to using the hash symbol followed by the relevant issue number your commit will be [automatically linked to an existing issue](https://help.github.com/articles/autolinked-references-and-urls/).

| Programmer A | Programmer B |
|--|--|
|<pre> $ git commit -m 'add homepage (index.html)<br>> Relates #1'</pre> |<pre> $ git commit -m 'add stylesheet (style.css)<br>> Relates #2'</pre>|
|<img src="images/step6GitFlowA.png" width="400" height="auto" alt="repo visual after step 1">|<img src="images/step6GitFlowB.png" width="400" height="auto" alt="repo visual after step 1">|

<!-- ***********************************************************-->
## Step 7 - Push your local version up to GitHub

At this point, your remote repo looks exactly the same as at the beginning. You need to push your changes.

| Programmer A | Programmer B |
|--|--|
|1. [Push](https://help.github.com/articles/pushing-to-a-remote/) the `create-homepage` branch up to the "origin" i.e. the GitHub repo that you cloned from.|1. [Push](https://help.github.com/articles/pushing-to-a-remote/) the `create-stylesheet` branch up to the "origin" i.e. the GitHub repo that you cloned from.|
|<pre>$ git push origin create-homepage</pre>|<pre>$ git push origin create-stylesheet</pre>|
|<img src="images/step7GitFlowA.png" width="400" height="auto" alt="repo visual after step 1">|<img src="images/step7GitFlowB.png" width="400" height="auto" alt="repo visual after step 1">|

<!-- ***********************************************************-->
## Step 8 - Create a pull request

| Programmer A | Programmer B |
|--|--|
|1. Navigate to the repository on GitHub.com and creates a [pull request](https://help.github.com/articles/creating-a-pull-request/#creating-the-pull-request).|1. Navigate to the repository on GitHub.com and creates a [pull request](https://help.github.com/articles/creating-a-pull-request/#creating-the-pull-request).|
|2. Add a descriptive title (e.g. `Creation of the homepage`) and leave a comment linking the pull request to the issue.|2. Add a descriptive title (e.g. `Creation of the stylesheet`) and leave a comment linking the pull request to the issue.|
|3. Select Programmer B as an [assignee](https://help.github.com/articles/assigning-issues-and-pull-requests-to-other-github-users/).| 3. Select Programmer A as an [assignee](https://help.github.com/articles/assigning-issues-and-pull-requests-to-other-github-users/)

Example of the pull request page on GitHub :

<img src="images/pull-request-open.png" width="500" height="auto" alt="open pull request page">

<!-- ***********************************************************-->
## Step 9 - You now have to accept the pull request of the other programmer:+1:
You should never merge your own pull requests. A PR gives the rest of your team the chance to review before your changes are merged into `master`. In your projects, you will be asking the other pair to do this.

| Programmer A | Programmer B |
|--|--|
|1. You have to review the changes and [merges the pull request](https://help.github.com/articles/merging-a-pull-request/#merging-a-pull-request-on-github) of Programmer B on GitHub.|1. You have to review the changes and [merges the pull request](https://help.github.com/articles/merging-a-pull-request/#merging-a-pull-request-on-github) of Programmer A on GitHub.|
|<img src="images/pull-request-tab.png" width="500" height="auto" alt="pull request tab button">|<img src="images/pull-request-tab.png" width="500" height="auto" alt="pull request tab button">|
|Now your remote repo looks like this: <br> <img src="images/step9GitFlowB.png" width="400" height="auto" alt="repo visual after step 1">|Now your remote repo looks like this: <br> <img src="images/step9GitFlowA.png" width="400" height="auto" alt="repo visual after step 1">|

After the two pull requests, the result will be the following:

<img src="images/step9GitFlowFinal.png" width="400" height="auto" alt="repo visual after step 1">



<!-- ***********************************************************-->
# Splitting the work
Your client has just called you and asked to improve heading on their [company website](https://piotrberebecki.github.io/git-workflow-workshop-for-two/).

There are two issues that when resolved will make the heading look really nice:

1. Spelling mistake in the heading (the word 'WORKSHOW' should be replaced with 'WORKSHOP')
1. The name of the css class in the heading needs to be updated so that existing styles in the `style.css` file can take effect (`class="some-heading"` should be replaced with `class="page-heading"`).

Current heading:

<img src="images/heading-before.png" width="500" height="auto" alt="git workflow workshop heading without css style">

When you apply the two changes above the heading will look like this:

<img src="images/heading-after.png" width="500" height="auto" alt="git workflow workshop heading with css style">


You decide that one of you **(Programmer A) will resolve the first issue** while the other person **(Programmer B) will resolve the second issue**. When you begin working on your weekly projects, you will always be pairing. So programmer A represents "pair 1" and programmer B represents "pair 2".

**Note: Only one line in the `index.html` file needs to be modified.**


<!-- ***********************************************************-->
## Step 1 - The two programmers have to pull the branch Master

1. You both have to pull the branch Master so that you have all the files up-to-date.

    ```sh
    $ git checkout master
    $ git pull origin master
    ```



<!-- ***********************************************************-->
## Step 2 - Raise these 2 new issues

| Programmer A | Programmer B |
|--|--|
|Create issue `Correct the class name of <h1> heading to match the existing class name in the css file` and assign it to Programmer B|Create issue `Fix spelling typo in <h1> heading` and assign it to Programmer A|

<!-- ***********************************************************-->
## Step 3 - Both programmers create one branch each and switch to them

| Programmer A | Programmer B |
|--|--|
|Create the branch `fix-typo-heading` :<br><pre> $ git branch fix-typo-heading</pre>|Create the branch `update-class-heading` :<br><pre> $ git branch update-class-heading</pre>|
|Leave the master branch by switching to the new branch :<br><pre>$ git checkout fix-typo-heading</pre>|Leave the master branch by switching to the new branch :<br><pre>$ git checkout update-class-heading</pre>

Note: You can achieve both steps _at once_ with `git checkout -b <new-branch-name>`.<br>
<img src="images/2step3GitFlow.png" width="500" height="auto" alt="repo visual after step 1">

<!-- ***********************************************************-->
## Step 4 - Both programmers open their `index.html` files and make one requested change each

| Programmer A | Programmer B |
|--|--|
|**Fix only the spelling typo** in the heading (WORKSHOW -> WORKSHOP). Please do not update the class name, this is dealt with by Programmer B. <br>```<h1 class="some-heading">GIT WORKFLOW WORKSHOP</h1>```|**update only the class name** of the heading (`class="some-heading"` -> `class="page-heading"`). Please do not fix the spelling mistake, this is dealt with by Programmer A.<br>```<h1 class="page-heading">GIT WORKFLOW WORKSHOW</h1>```|

<!-- ***********************************************************-->
## Step 5 - Both programmers save their `index.html` files and check status

1. Both programmers save their `index.html` files.

2. Both programmers check the [status](https://git-scm.com/docs/git-status) of their files, to confirm that `index.html` has been modified.

  ```sh
  $ git status
  ```



<!-- ***********************************************************-->
## Step 6 - Both programmers add the modified `index.html` file to the staging area

1. Both programmers add their modified `index.html` files to the staging area.

  ```sh
  $ git add index.html
  ```
<!-- ***********************************************************-->
## Step 7 - Both programmers commit their changes
1. Both programmers commit the changes. Don't forget the multi-line commit message with the referenced issue.

| Programmer A | Programmer B |
|--|--|
|<pre>$ git commit -m 'Fix typo in page heading<br>> Relates #[issue number]'</pre>|<pre>$ git commit -m 'Update class name in heading<br>> Relates #[issue number]'</pre>|

<img src="images/2step7GitFlow.png" width="600" height="auto" alt="repo visual after step 1">

<!-- ***********************************************************-->
## Step 8 - Programmer A switches to `master` branch and pulls down the remote `master` branch
We have so many programmers working on this project now, who knows what changes may have happened to the `master` branch since the last time we looked at the remote version that's on GitHub?

1. Programmer A switches to `master` branch.

  ```sh
  $ git checkout master
  ```

1. Programmer A [pulls](https://git-scm.com/docs/git-pull) the `master` branch from the remote (GitHub repo) to make sure that the local version of `master` is up to date with the remote (GitHub) version of `master`. (There should be no changes since neither of you has pushed any changes to the remote yet.) **It is a good practice to regularly check for changes on the remote before pushing your local changes.**

  ```sh
  $ git pull origin master
  ```

1. Programmer A switches back to the `fix-typo-heading` branch.

  ```sh
  $ git checkout fix-typo-heading
  ```



<!-- ***********************************************************-->
## Step 9 - Programmer A pushes `fix-typo-heading` branch to remote

1. Programmer A [pushes](https://help.github.com/articles/pushing-to-a-remote/) `fix-typo-heading` branch to remote

  ```sh
  $ git push origin fix-typo-heading
  ```

<img src="images/2step9GitFlow.png" width="500" height="auto" alt="repo visual after step 1">

<!-- ***********************************************************-->
## Step 10 - Programmer A creates a pull request

1. Programmer A navigates to the repository on GitHub.com and creates a [pull request](https://help.github.com/articles/creating-a-pull-request/#creating-the-pull-request).

    + Add a descriptive title (e.g. `Fix the spelling mistake in page heading`) and leave a comment linking the pull request to the issue.

    + Select Programmer B as an [assignee](https://help.github.com/articles/assigning-issues-and-pull-requests-to-other-github-users/).

    <img src="images/pull-request-open.png" width="500" height="auto" alt="open pull request page">



<!-- ***********************************************************-->
## Step 11 - Programmer B reviews the pull request

Programmer B [reviews the pull request](https://help.github.com/articles/about-pull-request-reviews/)

1. Step through each commit (in this case one)

2. Check the "Files changed" tab for a line-by-line breakdown.

2. Click "Review changes" and choose:
    + "Comment"
    + "Approve"
    + "Request changes"

<!-- ***********************************************************-->
## Step 12 - Programmer B merges the pull request :+1:

1. Programmer B [merges the pull request](https://help.github.com/articles/merging-a-pull-request/#merging-a-pull-request-on-github) on GitHub.com.

  <img src="images/pull-request-tab.png" width="500" height="auto" alt="pull request tab button">

2. Programmer B opens the website. Just go to the folder where the index.html file is and open it with your favorite web browser.

<img src="images/2step12GitFlow.png" width="250" height="auto" alt="repo visual after step 1">


<!-- ***********************************************************-->
## Step 13 - Programmer B switches to `master` branch, pulls the remote `master` branch, tries to merge it into `update-class-heading` branch and :collision: resolves merge conflicts :collision:

1. Programmer B switches to `master` branch.

  ```sh
  $ git checkout master
  ```

2. Programmer B [pulls](https://git-scm.com/docs/git-pull) the remote `master` branch to make sure that the latest version of the project is available locally.

  ```sh
  $ git pull origin master
  ```

  <img src="images/2step13(1)GitFlow.png" width="600" height="auto" alt="repo visual after step 1">

3. Programmer B switches back to the `update-class-heading` branch.

  ```sh
  $ git checkout update-class-heading
  ```

4. Programmer B tries to merge `master` branch into `update-class-heading` branch.

  ```sh
  $ git merge master
  ```

5. There should be a :collision: merge conflict :collision: since the line with the `<h1>` heading is different. [Merge conflict should be highlighted with HEAD and master markers](http://stackoverflow.com/questions/7901864/git-conflict-markers) as follows:

  ```html
  <body>

  <<<<<<< HEAD
      <h1 class="page-heading">GIT WORKFLOW WORKSHOW</h1>
  =======
      <h1 class="some-heading">GIT WORKFLOW WORKSHOP</h1>
  >>>>>>> master

  </body>
  ```

6. Programmer B removes HEAD and master markers and leaves only one line with `<h1>` heading so that both issues are addressed.

  ```html
  <body>

      <h1 class="page-heading">GIT WORKFLOW WORKSHOP</h1>

  </body>
  ```

7. Programmer B adds the `index.html` file to staging area and commits the changes occurred during the merge conflict.

  ```sh
  # First add to staging area
  $ git add index.html

  # Then commit changes
  $ git commit -m 'Fix merge conflict
  > Relates #<issue number> and #<issue number>'
  ```

<img src="images/2step13(2)GitFlow.png" width="400" height="auto" alt="repo visual after step 1">

<!-- ***********************************************************-->
## Step 14 - Programmer B pushes `update-class-heading` branch to remote

1. Programmer B [pushes](https://help.github.com/articles/pushing-to-a-remote/) `update-class-heading` branch to remote.

  ```sh
    $ git push origin update-class-heading
  ```

<img src="images/2step14GitFlow.png" width="400" height="auto" alt="repo visual after step 1">


<!-- ***********************************************************-->
## Step 15 - Programmer B creates a pull request

1. Programmer B navigates to the repository on GitHub.com and creates a [pull request](https://help.github.com/articles/creating-a-pull-request/#creating-the-pull-request) selecting `master` as a base branch and `update-class-heading` as a head branch. Please add a descriptive title (e.g. `Update class name in page heading`) and leave a comment linking the pull request with the issue `#<number>`. Please also select Programmer A as an [assignee](https://help.github.com/articles/assigning-issues-and-pull-requests-to-other-github-users/).



<!-- ***********************************************************-->
## Step 16 - Programmer A merges the pull request :+1:

1. Programmer A reviews and [merges the pull request](https://help.github.com/articles/merging-a-pull-request/#merging-a-pull-request-on-github) on GitHub.com.

<img src="images/2step16GitFlow.png" width="350" height="auto" alt="repo visual after step 1">

2. Programmer A opens the index.html file to double check the new heading style.

  <img src="images/heading-after.png" width="500" height="auto" alt="git workflow workshop heading with css style">



<!-- ***********************************************************-->
## That's it 😄 Thank you for checking out the 'Git Workflow Workshop for Two Programmers' :clap:  

***A summary of the above commands and what they do can be found [here](/images/git-flow-summary-table.png) in a neat little table.***
