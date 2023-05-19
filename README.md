# Gym-Git-Exercise-Solutions

## Bundle 1

- Exercise 1

```bash
gasa@Gasanna MINGW64 ~ (main)
$ mkdir git-Workouts

gasa@Gasanna MINGW64 ~ (main)
$ cd git-Workouts

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git init
Initialized empty Git repository in C:/Users/gasa/git-Workouts/.git/

gasa@Gasanna MINGW64 ~/git-Workouts (master)
$ git branch -m master main

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ touch index.html

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git add .

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git commit -m"Create file for exercise one and include two html files and one style.css file"
[main (root-commit) 6537ce0] Create file for exercise one and include two html files and one style.css file
 3 files changed, 29 insertions(+)
 create mode 100644 About.html
 create mode 100644 index.html
 create mode 100644 styles.css

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git remote add origin git@github.com:gasangw/git-Workouts.git

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git push -u origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 680 bytes | 226.00 KiB/s, done.
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), done.
To github.com:gasangw/git-Workouts.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git checkout -b dev
Switched to a new branch 'dev'

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git checkout -b test
Switched to a new branch 'test'

gasa@Gasanna MINGW64 ~/git-Workouts (test)
$ git checkout dev
Switched to branch 'dev'

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git branch -d test
Deleted branch test (was 6537ce0).
```
- Exercise 2
```bash
gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git add home.html

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git status
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   home.html

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    About.html
        deleted:    index.html
        deleted:    styles.css


gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git stash
Saved working directory and index state WIP on dev: 6537ce0 Create file for exercise one and include two html files and one style.css file

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git add about.html

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git stash
Saved working directory and index state WIP on dev: 6537ce0 Create file for exercise one and include two html files and one style.css file

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git stash list
stash@{0}: WIP on dev: 6537ce0 Create file for exercise one and include two html files and one style.css file
stash@{1}: WIP on dev: 6537ce0 Create file for exercise one and include two html files and one style.css file

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git add team.html

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git stash
Saved working directory and index state WIP on dev: 6537ce0 Create file for exercise one and include two html files and one style.css file

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git stash list
stash@{0}: WIP on dev: 6537ce0 Create file for exercise one and include two html files and one style.css file
stash@{1}: WIP on dev: 6537ce0 Create file for exercise one and include two html files and one style.css file
stash@{2}: WIP on dev: 6537ce0 Create file for exercise one and include two html files and one style.css file

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git stash pop stash@{1}
On branch dev
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   About.html

no changes added to commit (use "git add" and/or "git commit -a")
Dropped stash@{1} (2312d08fcfe412ebe236b777250f9c71329827be)

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git stash pop stash@{2}
error: Your local changes to the following files would be overwritten by merge:
        About.html
Please commit your changes or stash them before you merge.
Aborting
On branch dev
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   About.html

no changes added to commit (use "git add" and/or "git commit -a")
The stash entry is kept in case you need it again.

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git add .

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git commit -m"Create about and home pages"
[dev 5ae880e] Create about and home pages
 1 file changed, 2 insertions(+), 3 deletions(-)

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git stash pop
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html

Dropped refs/stash@{0} (5bbe5f58aa8ee69db36513794afbb426d5054634)

gasa@Gasanna MINGW64 ~/git-Workouts (dev)
$ git reset --hard
HEAD is now at 5ae880e Create about and home pages

$ git push origin dev
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 392 bytes | 392.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'dev' on GitHub by visiting:
remote:      https://github.com/gasangw/git-Workouts/pull/new/dev
remote:
To github.com:gasangw/git-Workouts.git
 * [new branch]      dev -> dev
```

## Bundle 2

- Exercise 1
```bash
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git checkout -b ft/bundle-2
Switched to a new branch 'ft/bundle-2'

gasa@Gasanna MINGW64 ~/git-Workouts (ft/bundle-2)
$ git add .

gasa@Gasanna MINGW64 ~/git-Workouts (ft/bundle-2)
$ git commit -m"Add services page and edit the title and create a heading inside"
[ft/bundle-2 019262b] Add services page and edit the title and create a heading inside
 1 file changed, 12 insertions(+)
 create mode 100644 services.html

gasa@Gasanna MINGW64 ~/git-Workouts (ft/bundle-2)
$ git push origin ft/bundle-2
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 577 bytes | 577.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'ft/bundle-2' on GitHub by visiting:
remote:      https://github.com/gasangw/git-Workouts/pull/new/ft/bundle-2
remote:
To github.com:gasangw/git-Workouts.git
 * [new branch]      ft/bundle-2 -> ft/bundle-2

```

- Exercise 2

```bash
gasa@Gasanna MINGW64 ~/git-Workouts (ft/bundle-2)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git checkout -b ft/service-redesign
Switched to a new branch 'ft/service-redesign'

gasa@Gasanna MINGW64 ~/git-Workouts (ft/service-redesign)
$ git pull origin main
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 631 bytes | 157.00 KiB/s, done.
From github.com:gasangw/git-Workouts
 * branch            main       -> FETCH_HEAD
   6537ce0..38e8795  main       -> origin/main
Updating 6537ce0..38e8795
Fast-forward
 services.html | 12 ++++++++++++
 1 file changed, 12 insertions(+)
 create mode 100644 services.html

gasa@Gasanna MINGW64 ~/git-Workouts (ft/service-redesign)
$ git add .

gasa@Gasanna MINGW64 ~/git-Workouts (ft/service-redesign)
$ git commit -m"Add a paragraph"
[ft/service-redesign dce4645] Add a paragraph
 1 file changed, 1 insertion(+)

gasa@Gasanna MINGW64 ~/git-Workouts (ft/service-redesign)
$ git push origin ft/service-redesign
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 329 bytes | 329.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote:
remote: Create a pull request for 'ft/service-redesign' on GitHub by visiting:
remote:      https://github.com/gasangw/git-Workouts/pull/new/ft/service-redesign
remote:
To github.com:gasangw/git-Workouts.git
 * [new branch]      ft/service-redesign -> ft/service-redesign

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git pull origin main
From github.com:gasangw/git-Workouts
 * branch            main       -> FETCH_HEAD
Updating 6537ce0..38e8795
Fast-forward
 services.html | 12 ++++++++++++
 1 file changed, 12 insertions(+)
 create mode 100644 services.html

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git add .

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git commit -m"edit the services page"
[main 9a1ecdc] edit the services page
 1 file changed, 2 insertions(+), 1 deletion(-)

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 340 bytes | 340.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:gasangw/git-Workouts.git
   38e8795..9a1ecdc  main -> main

gasa@Gasanna MINGW64 ~/git-Workouts (ft/service-redesign)
$ git checkout main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git pull origin main
From github.com:gasangw/git-Workouts
 * branch            main       -> FETCH_HEAD
Updating 6537ce0..38e8795
Fast-forward
 services.html | 12 ++++++++++++
 1 file changed, 12 insertions(+)
 create mode 100644 services.html

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git add .

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git commit -m"edit the services page"
[main 9a1ecdc] edit the services page
 1 file changed, 2 insertions(+), 1 deletion(-)

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 340 bytes | 340.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:gasangw/git-Workouts.git
   38e8795..9a1ecdc  main -> main

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git checkout ft/service-redesign
Switched to branch 'ft/service-redesign'

gasa@Gasanna MINGW64 ~/git-Workouts (ft/service-redesign)
$ git diff ft/service-redesign main
diff --git a/services.html b/services.html
index ce0bdbe..ddea37d 100644
--- a/services.html
+++ b/services.html
@@ -7,7 +7,7 @@
     <title>Services Page</title>
 </head>
 <body>
-    <h1>Checkout our services plzzz</h1>
-    <p>I love serving meals</p>
+    <h1>Checkout services</h1>
+    <p>hello tomato</p>
 </body>
 </html>
\ No newline at end of file

gasa@Gasanna MINGW64 ~/git-Workouts (ft/service-redesign)
$ git merge main
Auto-merging services.html
CONFLICT (content): Merge conflict in services.html
Automatic merge failed; fix conflicts and then commit the result.

```

# Bundle 3
- Exercise 1
```bash
gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git checkout -b ft/team-page
Switched to a new branch 'ft/team-page'

gasa@Gasanna MINGW64 ~/git-Workouts (ft/team-page)
$ git add .

gasa@Gasanna MINGW64 ~/git-Workouts (ft/team-page)
$ git commit -m"Create new file called teams and add changes"
[ft/team-page 87771ba] Create new file called teams and add changes
 1 file changed, 12 insertions(+)
 create mode 100644 team.html

gasa@Gasanna MINGW64 ~/git-Workouts (ft/team-page)
$ git push origin ft/team-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 483 bytes | 241.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/team-page' on GitHub by visiting:
remote:      https://github.com/gasangw/git-Workouts/pull/new/ft/team-page
remote:
To github.com:gasangw/git-Workouts.git
 * [new branch]      ft/team-page -> ft/team-page

gasa@Gasanna MINGW64 ~/git-Workouts (ft/team-page)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git checkout -b ft/contact-page
Switched to a new branch 'ft/contact-page'

gasa@Gasanna MINGW64 ~/git-Workouts (ft/contact-page)
$ git checkout ft/team-page
Switched to branch 'ft/team-page'

gasa@Gasanna MINGW64 ~/git-Workouts (ft/team-page)
$ git log --oneline
87771ba (HEAD -> ft/team-page, origin/ft/team-page) Create new file called teams and add changes
9a1ecdc (origin/main, main, ft/contact-page) edit the services page
38e8795 Merge pull request #1 from gasangw/ft/bundle-2
019262b (origin/ft/bundle-2, ft/bundle-2) Add services page and edit the title and create a heading inside
6537ce0 Create file for exercise one and include two html files and one style.css file

gasa@Gasanna MINGW64 ~/git-Workouts (ft/team-page)
$ git checkout ft/contact-page
Switched to branch 'ft/contact-page'

gasa@Gasanna MINGW64 ~/git-Workouts (ft/contact-page)
$ git cherry-pick 87771ba
[ft/contact-page 9b89078] Create new file called teams and add changes
 Date: Fri May 19 09:14:01 2023 +0200
 1 file changed, 12 insertions(+)
 create mode 100644 team.html

gasa@Gasanna MINGW64 ~/git-Workouts (ft/contact-page)
$ git add .

gasa@Gasanna MINGW64 ~/git-Workouts (ft/contact-page)
$ git commit -m"Add teams file using git cherry-pick"
[ft/contact-page f5245e4] Add teams file using git cherry-pick
 1 file changed, 1 insertion(+)

gasa@Gasanna MINGW64 ~/git-Workouts (ft/contact-page)
$ git push origin ft/contact-page
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 753 bytes | 753.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/contact-page' on GitHub by visiting:
remote:      https://github.com/gasangw/git-Workouts/pull/new/ft/contact-page
remote:
To github.com:gasangw/git-Workouts.git
 * [new branch]      ft/contact-page -> ft/contact-page

```

- Exercise 2
```bash
gasa@Gasanna MINGW64 ~/git-Workouts (ft/faq-page)
$ git checkout -b ft/home-page-redesign
Switched to a new branch 'ft/home-page-redesign'

gasa@Gasanna MINGW64 ~/git-Workouts (ft/home-page-redesign)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git add .

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git commit -m"update the paragraph"
[main c00d846] update the paragraph
 1 file changed, 1 insertion(+), 1 deletion(-)

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 306 bytes | 102.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:gasangw/git-Workouts.git
   9a1ecdc..c00d846  main -> main

gasa@Gasanna MINGW64 ~/git-Workouts (main)
$ git checkout ft/home-page-redesign
Switched to branch 'ft/home-page-redesign'

gasa@Gasanna MINGW64 ~/git-Workouts (ft/home-page-redesign)
$ git rebase main
Successfully rebased and updated refs/heads/ft/home-page-redesign.

gasa@Gasanna MINGW64 ~/git-Workouts (ft/home-page-redesign)
$ git add .

gasa@Gasanna MINGW64 ~/git-Workouts (ft/home-page-redesign)
$ git commit -m"Rebase changes in the main"
[ft/home-page-redesign f88b1f3] Rebase changes in the main
 1 file changed, 1 insertion(+), 1 deletion(-)

gasa@Gasanna MINGW64 ~/git-Workouts (ft/home-page-redesign)
$ git push origin ft/home-page-redesign
Enumerating objects: 15, done.
Counting objects: 100% (15/15), done.
Delta compression using up to 8 threads
Compressing objects: 100% (14/14), done.
Writing objects: 100% (14/14), 1.51 KiB | 772.00 KiB/s, done.
Total 14 (delta 8), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (8/8), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/gasangw/git-Workouts/pull/new/ft/home-page-redesign
remote:
To github.com:gasangw/git-Workouts.git
 * [new branch]      ft/home-page-redesign -> ft/home-page-redesign

```

# Bundle 5
- Exercise 1

[Github-pages-link](https://gasangw.github.io/git-Workouts/)

- Exercise 2
```bash
gasa@Gasanna MINGW64 ~ (main)
$ git clone git@github.com:gasangw/git-cafe-exercise.git
Cloning into 'git-cafe-exercise'...
remote: Enumerating objects: 107, done.
remote: Counting objects: 100% (107/107), done.
remote: Compressing objects: 100% (101/101), done.
remote: Total 107 (delta 5), reused 104 (delta 4), pack-reused 0
Receiving objects: 100% (107/107), 1.95 MiB | 1.22 MiB/s, done.
Resolving deltas: 100% (5/5), done.

gasa@Gasanna MINGW64 ~ (main)
$ cd git-cafe-exercise

gasa@Gasanna MINGW64 ~/git-cafe-exercise (main)
$ git add .

gasa@Gasanna MINGW64 ~/git-cafe-exercise (main)
$ git commit -m"Edit the title of the main content"
[main 699f1d2] Edit the title of the main content
 1 file changed, 1 insertion(+), 1 deletion(-)

gasa@Gasanna MINGW64 ~/git-cafe-exercise (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 326 bytes | 326.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:gasangw/git-cafe-exercise.git
   d1d3f9c..699f1d2  main -> main
```

## Bundle 6

- Exercise 1
```bash

gasa@Gasanna MINGW64 ~/git-cafe-exercise (main)
$ git checkout -b feature_menu
Switched to a new branch 'feature_menu'

gasa@Gasanna MINGW64 ~/git-cafe-exercise (feature_menu)
$ git add .

gasa@Gasanna MINGW64 ~/git-cafe-exercise (feature_menu)
$ git status
On branch feature_menu
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   Menu.html


gasa@Gasanna MINGW64 ~/git-cafe-exercise (feature_menu)
$ git commit -m"Create menu file"
[feature_menu 24fe47a] Create menu file
 1 file changed, 12 insertions(+)
 create mode 100644 Menu.html

gasa@Gasanna MINGW64 ~/git-cafe-exercise (feature_menu)
$ git push origin feature_menu
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 483 bytes | 483.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'feature_menu' on GitHub by visiting:
remote:      https://github.com/gasangw/git-cafe-exercise/pull/new/feature_menu
remote:
To github.com:gasangw/git-cafe-exercise.git
 * [new branch]      feature_menu -> feature_menu

```
- Exercise 2
```bash
asa@Gasanna MINGW64 ~/git-cafe-exercise (feature_menu)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

gasa@Gasanna MINGW64 ~/git-cafe-exercise (main)
$ git checkout -b feature_bug_fix
Switched to a new branch 'feature_bug_fix'

gasa@Gasanna MINGW64 ~/git-cafe-exercise (feature_bug_fix)
$ git add .

gasa@Gasanna MINGW64 ~/git-cafe-exercise (feature_bug_fix)
$ git commit -m"Update the title for the file from menu to contact"
[feature_bug_fix d471481] Update the title for the file from menu to contact
 1 file changed, 1 insertion(+), 1 deletion(-)

gasa@Gasanna MINGW64 ~/git-cafe-exercise (feature_bug_fix)
$ git push origin feature_bug_fix
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 322 bytes | 161.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote:
remote: Create a pull request for 'feature_bug_fix' on GitHub by visiting:
remote:      https://github.com/gasangw/git-cafe-exercise/pull/new/feature_bug_fix
remote:
To github.com:gasangw/git-cafe-exercise.git
 * [new branch]      feature_bug_fix -> feature_bug_fix

```

- Exercise 3
```bash
gasa@Gasanna MINGW64 ~/git-cafe-exercise (feature_bug_fix)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

gasa@Gasanna MINGW64 ~/git-cafe-exercise (main)
$ git checkout -b feature_hotfix
Switched to a new branch 'feature_hotfix'

gasa@Gasanna MINGW64 ~/git-cafe-exercise (feature_hotfix)
$ git add .

gasa@Gasanna MINGW64 ~/git-cafe-exercise (feature_hotfix)
$ git commit -m"Update the telephone in index-4.html"
[feature_hotfix 3a11f58] Update the telephone in index-4.html
 1 file changed, 1 insertion(+), 1 deletion(-)

gasa@Gasanna MINGW64 ~/git-cafe-exercise (feature_hotfix)
$ git push origin feature_hotfix
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 309 bytes | 309.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote:
remote: Create a pull request for 'feature_hotfix' on GitHub by visiting:
remote:      https://github.com/gasangw/git-cafe-exercise/pull/new/feature_hotfix
remote:
To github.com:gasangw/git-cafe-exercise.git
 * [new branch]      feature_hotfix -> feature_hotfix

```