# You've downloaded [Git](https://git-scm.com), now what?
By this point you've at least downloaded the [Git](https://git-scm.com) binary and are likely wondering what to do for the different options that show up during the installation process.  Since [Git](https://git-scm.com) was designed for Linus Torvalds to manage the development of the [Linux kernel](https://github.com/torvalds/linux) without necessarily having to interact with people directly, it wasn't built with the Windows operating system in mind.  That said, we're here to give you some tips on standard configuration options to help you avoid expending too many keystrokes and ensure that your workflow __works__ across your team's workstations.

# Barebones configuration options
When you commit changes to a [Git](https://git-scm.com) repository __you are identified as making the changes__.  This means any changes to the code base made by anyone can always be tracked and dialog can take place between the committer and the repository owner.  There are two big configuration options that you'll need to set to make your life easier here:

```
git config --global user.name "FirstName LastName"
git config --global user.email yourEmailAddress@your-domain.com
```

The default string encoding on Windows uses a different character when you hit the `return`/`enter` key than non-Windows machines.  The three lines below give you the options to use depending on your organization's use case.  At FCPS two of the people on our team work from machines running OSX, while the other folks in the shop use machines running Windows.

```
# If you're working in a predominantly Windows shop use the line below
git config --global core.autocrlf true

# If you work with a machine running any non-Windows OS use this line
git config --global core.autocrlf input

# If your code will only ever run on Windows machines and is designed only from Windows machines use:
git config --global core.autocrlf false
```

# Setting up a location for your templates

```
mkdir -p ${HOME}/.git_template/{hooks,exclude,commit}
cd .git_template
git init .
git commit -a -m "Initial commit for Git templates and other configuration options for my workflow"
```

Now you've not only set up the initial directory, but are even using [Git](https://git-scm.com) to track any changes to any of the files you'll use to set up default templates and configuration options for your workflow.  Holy recursion Batman...



