cd /users/raynovarina/sites/AtomProjects/harp/canvas-bubbles-plume/

per: https://codepen.io/SylvaShadow/pen/vEjRde

Created and initialized harp app:

$ cd /users/raynovarina/sites/AtomProjects/harp/
$ md canvas-bubbles-plume
$ cd canvas-bubbles-plume/
$ md js
$ md css
$ echo "This is /harp/canvas-bubbles-plume/index.html via localhost:9002" > index.html

Start harp server:
$ harp server -p 9002

Access via localhost:9002
============================

Add package.json and Procfile files for Heroku deploy:
  package.json:

    {
      "name": "harp-heroku-canvas-bubbles-plume",
      "version": "0.0.1",
      "description": "Harp server App: javascript/canvas/animated bubbles",
      "dependencies": {
        "harp": "*"
      }
    }

  Procfile:

    web: harp server --port $PORT

At github account, create new repository: harp-heroku-canvas-bubbles-plume and then
locally.
  $ git init
  $ git remote add origin https://github.com/RayNovarina/harp-heroku-canvas-bubbles-plume.git

Create Heroku app:
  $ heroku create harp-canvas-bubbles-plume-9403

$ git remote -v
  heroku  https://git.heroku.com/harp-canvas-bubbles-plume-9403.git (fetch)
  heroku  https://git.heroku.com/harp-canvas-bubbles-plume-9403.git (push)
  origin  https://github.com/RayNovarina/harp-heroku-canvas-bubbles-plume.git (fetch)
  origin  https://github.com/RayNovarina/harp-heroku-canvas-bubbles-plume.git (push)

Deploy changes to github and heroku:
  $ git add .
  $ git commit -am "First Harp + Heroku commit"
  $ git push origin master
  $ git push heroku master

View on Heroku:

  https://harp-canvas-bubbles-plume-94037.herokuapp.com shows:

  Welcome to harp/canvas-bubbles-plume.
  Deployed locally at http://localhost:9002/
  Deployed on Heroku at https://harp-canvas-bubbles-plume-94037.herokuapp.com/

------------------------------
Replace with github exploding exploding profiles code and redeploy working
version to Heroku.

Erase all harp files except for package.json, Procfile.
Clone from github exploding-effects repository into projects/exploding-effects
folder and move those folder into harp/canvas-dots.

Because we have no layout.jade file, hard seems to set the app root at
harp/canvas-dots.

Load app as is from localhost:9000/pages/management.html

Fixup a lot of problems.
harp less preprocessor seems to only be able to find management.less file if
it is at app root (harp/canvas-dots). Gets converted to a .css file when
loaded.

commit and push fixed version to github.
push to heroku.

load heroku version via https://harp-canvas-bubbles-plume-94037.herokuapp.com/pages/management.html

===============================
