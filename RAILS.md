# Boostrapping a Rails project

## Creating a Root Directory For Your Rails Project

One creates a Rails project from the parent directory, using the command, *rails new my-project-root*.  However, one needs to have Rails installed before one can do this.
And, typically, Rails is simply another gem bundled within the my-project-root/Gemfile.

So, there's a bit of paradox:  to create the project root, you need Rails;  but, you won't get Rails until you *bundle* within the project root.  What is to be done?  One
installs a version of Rails independent of the project being created--but with the
desired version (of Rails).  One then uses that version of Rails simply to create the project root (sub) directory, and, from that moment onward, one can ignore the first version of Rails.

Assume that you will create your new project root within a directory called *repos*.
Cd to *repos*, and then ensure that you are using the Ruby you want, e.g.:
```bash
cd repos
chruby 2.5.3 # The latest at the time of this writing
```
Now install the desired version of Rails as a Gem within this version of Ruby:
```bash
gem install rails # get the latest, what the heck.
```
Now, use Rails to create a subdirectory for the new project:
```bash
rails new my-project-root <options>
```
The options I often use are these:

-d postgresql --skip-spring --skip-test

If this is an API-only Rails server, add --api

## Create and Connect to a Github Repository

### Create a github repository to hold your new project.  When I do this, I create an empty project--I don't ask github to pre-initialize a README.md, nor to set up a Rails-ish .gitignore, nor anything else--because, I've already used *rails new* to create all of that within the root directory.

You need only one thing from the github:  you need the link to the repo with which you would ordinarily call git clone.  Don't call git clone, but, do grab the link in the copy-paste buffer.
### Initialize git in your root directory:
```bash
cd repos/my-project-root
git init
```
### Perform the initial commit in this git repo:
```bash
git add -A
git commit -m "Initial Commit" # Or, call it whatever you prefer.
```
### Create the git *remote* *origin*, and push the master branch
```bash
git remote add origin git-clone-link-to-your-github-repo
git push origin master
```

If you refresh the Web page of your github repo, you should see your project with all of its Rails stuff.


