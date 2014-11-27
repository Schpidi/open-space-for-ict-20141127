# Pitch at the Open Space for ICT 27th November 2014.

## Running presentation

Point your browser to the [online presentation](http://schpidi.github.io/open-space-for-ict-20141127)
or serve it locally.

```bash
git clone
cd
npm install
grunt serve
```

## Creating presentation

After creating a new repository at GitHub or GitLab without initializing it
run the following.

```bash
mkdir presentation
cd presentation
git init
git checkout -b gh-pages
git remote add origin git@github.com:Schpidi/open-space-for-ict-20141127.git
git submodule add https://github.com/Schpidi/reveal.js.git
cd reveal.js/
git checkout eox_box
git pull origin eox_box
cd ..
git add reveal.js/

ln -s reveal.js/Gruntfile.js Gruntfile.js
ln -s reveal.js/package.json package.json
npm install

echo "node_modules/" >> .gitignore
git add Gruntfile.js package.json .gitignore
git commit -m "Adding reveal.js."

cp reveal.js/index.html .
# Edit index.html to your liking
git commit index.html -m "Adding presentation."

vi README.md
vi LICENSE
git add README.md LICENSE
git commit -m "Adding readme and license."

git push -u origin gh-pages
```
