# workflow
Dotfiles and background on how to use my basic coding workflow. This flow
is not for everyone. In particular, this assumes that you wish to do most
of your work directly inside your terminal through vim. If you wish to
substitute a different text editor, this will still work but this specific
workflow may be less well-suited to it.

## General Notes
### Keyboard vs. Mouse
When possible, always use the keyboard in place of the mouse. This sounds
silly, but grabbing your mouse will usually take at least a second, and
requires a good deal of focus and precision to hit exactly what you want. This
is distracting and can break your concentration, which can be especially
troublesome if you're in a flow state. Furthermore, it can slow you down
significantly over time, especially if you're doing something that requires
you to change from your mouse to your keyboard every few seconds. Using vim
automatically helps to cut down on this quite a lot (especially if used
properly), but I encourage everyone who spends a lot of time on their
computer to learn as many keyboard shortcuts as possible. The goal (in my
opinion) should be to almost completely avoid the mouse while developing unless
doing something that you're deliberately taking your time with.

### Continuously Learning
This is one of the most important things to learn from this whole guide.
Programming is a rather unique field in that almost everything we use is
designed by people, often with a goal of making things understandable and easy
to use. Compare this with, for example, biology, which revolves around the
study of things that humans (generally) had no part in designing, and which is
as a result enormously complex.

In general, if you identify something that seems badly designed or inefficient
while programming, I recommend doing a bit of research on it through google.
In general, you will find one of two things to be true:
  1. There is at least one known and accepted solution to it, or
  1. There is a large amount of very angry discussion about it
Given that the latter is usually very easy to find, it tends to be quite easy
to discover whether or not a solution exists. From here, it remains only to
determine the details and integrate it into one's workflow. I strongly
recommend going through this process even for things that are even only a bit
inconvenient, as small savings add up very rapidly.


## Initial Setup (One Time)
### .bashrc
This is a file that's stored in your home directory, and automatically run
anytime you open terminal. You can use this to configure your command line to
work however you want, including adding information to your prompt, or (my
personal favorite) enable vim keybindings on the command line. This last is
very helpful if, for example, you need to change the first flag in a very long
list of flags on a command. The alternative in this case would be holding the
left arrow key for up to several seconds, which is very inefficient and
distracting.

### .vimrc
More will be said on vim in its own dedicated section, but as an overview,
this is a file that will be stored at a user's home directory that will be
referenced whenever vim is started, allowing a user to configure vim as they
please. Furthermore, it is possible to have an extremely functional vim setup
which can be created properly on a new machine by simply copying a .vimrc to
the new machine's home directory. My own .vimrc is included in this repo, and
I feel it is a good starting place. I highly encourage modifying one's vim
setup to best suit one's specific needs.
