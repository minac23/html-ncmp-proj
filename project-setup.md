*make sure Git is installed before installing node.js

# create a project folder
First create a new project folder and open the folder in VS Code.

# initialize an empty git repo
git init
This will create a .git folder in your project folder.

# create an html file (index.html for example)

# push first commit into local repo
git add <index.html>
git commit -m <"message">

# link local repo to remote repo (if using)
git remote add origin <your remote repo URL>

Git will ask for a personal access token for authentication. 
https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token
Set the name and expiration of the access token to your preference.
In "scopes" make sure to choose at least "repo" checkbox.
Make sure to copy and keep access token safe.

# push first commit into remote repo 
git push -u origin master
Press enter to all defaults.

All future commmits
git push

# cloning an online repo to your local repo
Create new folder in selected directory.

mkrdir <folder name>
cd <folder name>
git status --> make sure does not have anything in it, should be empty
git clone <replace this with our remote repo URL>

# verify node is installed
node -v
npm -v

# intialize folder as an NPM project (create package.json file)
npm init
accept defaults by pressing enter
this will create a package.json file

# install lite server
npm install lite-server --save-dev
no version given on lite server, this will install the latest version
--save-dev means installed as a project dependency, when project is built for deployment, it will not be included in the final build files
this will create a package-lock.json

# add scripts to package.json file (example page below, make sure to include scripts with a "," after except for last script)
{
  "name": "portfolio-project",
  "version": "1.0.0",
  "description": "portfolio project",
  "main": "index.js",
  "scripts": {
    "start": "npm run lite",
    "lite": "lite-server",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/minac23/port-proj-files.git"
  },
  "author": "Celine",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/minac23/port-proj-files/issues"
  },
  "homepage": "https://github.com/minac23/port-proj-files#readme",
  "devDependencies": {
    "lite-server": "^2.6.1"
  }
}

# npm start
npm start
this should open html page (index.html) in VS code, make change and save, and the browser should immediately refresh

# set up .gitignore
create a file in your project directory named .gitignore (note: starts with a period)
then add 
node_modules

git add .
git commit
git push

# install dependencies
install lite server if have not done so already
 
install jquery
npm install jquery@3.5.1 popper.js@1.16.1
install bootstrap
npm install bootstrap@4.5.2
this will auto update the package.json file

# update bootstrap code
<head>
    <!-- Required meta tags always come first -->
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.min.css" />

    <title></title>
</head>

# add javascript files
after </footer> but before closing </body> tag

    </footer>

    <!-- jQuery must come first, then Popper.js, then the Bootstrap JavaScript plugins.-->
    <script src="node_modules/jquery/dist/jquery.slim.min.js"></script>
    <script src="node_modules/popper.js/dist/umd/popper.min.js"></script>
    <script src="node_modules/bootstrap/dist/js/bootstrap.min.js"></script>

</body>