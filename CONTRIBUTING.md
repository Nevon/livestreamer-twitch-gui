# Contributing to Livestreamer-Twitch-GUI

Want to get involved? Thanks! There are plenty of ways to help!


## Reporting issues

A bug is a *demonstrable problem* that is caused by the code in the repository. Good bug reports are extremely helpful - thank you!

Please read the following guidelines before you [report an issue][issues]:

1. **Use the GitHub issue search** — check if the issue has already been reported. If it has been, please comment on the existing issue.

2. **Check if the issue has been fixed** — the latest `master` or development branch may already contain a fix.

3. **Isolate the demonstrable problem** — make sure that the code in the project's repository is *definitely* responsible for the issue.

Please try to be as detailed as possible in your report too. What is your environment? What steps will reproduce the issue? What would you expect to be the outcome? All these details will help people to assess and fix any potential bugs.


## Feature requests

Feature requests are welcome. But take a moment to find out whether your idea fits with the scope and aims of the project. It's up to *you* to make a strong case to convince the project's developers of the merits of this feature. Please provide as much detail and context as possible.


## Developing and building
Livestreamer-Twitch-GUI is based on [Node-Webkit (NW)][node-webkit]. NW has to be installed on your machine in order to run this program - using a browser does not work. Have a look at the [NW wiki page][nw-wiki] to get some more informations on how to run NW-apps. Also please ensure that [Node.js (including npm)][nodejs] is installed so you can build the program.

Building is simple:

```bash
# globally install grunt-cli and bower - may require administrator privileges
npm install -g grunt-cli bower
# locally install all npm and bower dependencies
npm install
# build and compile - executable will be created inside the build/releases folder
grunt release
```

Run `grunt --help` to list all other available grunt tasks.

There are two different methods to run the program while developing:

1. **the "easy" method**
   Simply run `grunt dev`. This task builds the project to the `/build/tmp` folder with enabled debug flags and also starts a watcher task which rebuilds changed content from the `/src` folder. Now start NW (`nw build/tmp`) and open the developer-console by clicking on the button inside the menubar.

2. **the "source" method**
   Another way of running the program is by starting it directly from the `/src` folder (`nw src`). Before you can do this, you need to run the `grunt build` task once and copy the generated `/build/tmp/metadata.json` file into the `/src` folder. By using this method, only the stylesheets need to be built: run `grunt less:source` or start the watcher task `grunt watch:lesssource`.


## Pull requests

Good pull requests - patches, improvements, new features - are a fantastic help. They should remain focused in scope and avoid containing unrelated commits.

**Please ask first** before embarking on any significant pull request (e.g. implementing features, refactoring code, porting to a different language), otherwise you risk spending a lot of time working on something that the project's developers might not want to merge into the project.

Please adhere to the coding conventions used throughout a project (indentation, white space, accurate comments, etc.) and any other requirements (such as test coverage).

Adhering to the following this process is the best way to get your work included in the project:

1. [Fork][howto-fork] the project, clone your fork, and configure the remotes:
   ```bash
   # Clone your fork of the repo into the current directory
   git clone git@github.com:<YOUR-USERNAME>/livestreamer-twitch-gui.git
   # Navigate to the newly cloned directory
   cd livestreamer-twitch-gui
   # Assign the original repo to a remote called "upstream"
   git remote add upstream https://github.com/bastimeyer/livestreamer-twitch-gui.git
   ```

2. If you cloned a while ago, get the latest changes from upstream
   ```bash
   git checkout master
   git pull upstream master
   ```

3. Create a new topic branch (off the main project branch) to contain your feature, change, or fix:
   ```bash
   git checkout -b <TOPIC-BRANCH-NAME>
   ```

4. Commit your changes in logical chunks. Please adhere to these [git commit message guidelines][howto-format-commits] or your code is unlikely be merged into the project. Use git's [interactive rebase][howto-rebase] feature to tidy up your commits before making them public.

5. Locally merge (or rebase) the upstream branch into your topic branch:
   ```bash
   git pull [--rebase] upstream master
   ```

6. Push your topic branch up to your fork:
   ```bash
   git push origin <TOPIC-BRANCH-NAME>
   ```

7. [Open a Pull Request][howto-open-pull-requests] with a clear title and description.

**IMPORTANT**: By submitting a patch, you agree to allow the project owners to license your work 
under the terms of the [MIT License][license].


## Acknowledgements

This contributing guide has been adapted from [HTML5 boilerplate's guide][ref-h5bp].


  [license]: https://github.com/bastimeyer/livestreamer-twitch-gui/blob/master/LICENSE
  [issues]: https://github.com/bastimeyer/livestreamer-twitch-gui/issues
  [howto-fork]: https://help.github.com/articles/fork-a-repo
  [howto-rebase]: https://help.github.com/articles/interactive-rebase
  [howto-format-commits]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
  [howto-open-pull-requests]: https://help.github.com/articles/using-pull-requests
  [node-webkit]: https://github.com/rogerwang/node-webkit
  [nw-wiki]: https://github.com/rogerwang/node-webkit/wiki
  [nodejs]: http://nodejs.org/
  [ref-h5bp]: https://github.com/h5bp/html5-boilerplate/blob/master/CONTRIBUTING.md
