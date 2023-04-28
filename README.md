# LibSubModule

push local repo to Github

- following https://docs.github.com/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github

- create completely empty repo on Github LibSubModule

…or create a new repository on the command line
echo "# LibSubModule" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M master
git remote add origin https://github.com/johnraz99/LibSubModule.git
git push -u origin master

…or push an existing repository from the command line
git remote add origin https://github.com/johnraz99/LibSubModule.git
git branch -M master
git push -u origin master

To link the projects 
- first created the github repos
- then clone LibSubModule 
- then git submodule add (had to remove overlapping dir Mathlib)
$ git submodule add https://github.com/johnraz99/Mathlib.git LibSubModule/vendor/Mathlib
- save link to Github
$ git commit -m "add MathLib submodule"
$ git push origin

- for repo with the removed dir MathLib, after pull had to reinstantiate MathLib dir
$ git pull 
$ git submodule update --init