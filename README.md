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
