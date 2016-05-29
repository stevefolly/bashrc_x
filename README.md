# bashrc_x
A simple mechanism to organise your .bashrc script

Quite often when customizing a .bashrc file over time, it builds up with cruft and stuff all over the place that you can't remember when and why you added it.

This idea stems from general good practices in coding - i.e. separation of concerns, single responsibility principle, etc.

## Single modification to .bashrc

Add the following few lines to your `.bashrc` file:

```
for f in ~/.bashrc_* ; do
  source $f
done
```


Now, when you need customisation for a particular project, you can localize that to a separate file:

```
# bashrc_project1
export PATH=$PATH:/usr/local/project1/bin
alias foo='project1_foo'
```

# Example: bashrc_git

My personal git customisations:

```
# git customisation
alias gg='git gui &'
alias gka='gitk --all &'
```

Create as many different `.bashrc_*` files as necessary.

# Cleaning up

When you've finished working on a project, simply remove that `.bashrc_project` file.
