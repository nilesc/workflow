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

### Putting this in to Practice
For this to become natural, you will need to use and repeat the various
actions described in this guide. Be constantly on the lookout for situations
where these tools are appropriate, and be sure to use them. Personally, if I
do something in an inefficient way while trying to learn a tool that improves
that thing, I will often go as far as to deliberately undo that action and
redo it in the efficient way. This is a good way to learn in the long run, but
may be a bit extreme for some people in the short term.

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

## tmux
tmux is a terminal multiplexer. In practice, this allows you to turn a single
terminal prompt into multiple, either in the form of splits on your screen, or
in the form of multiple pages which can be swapped between, among other
options. Furthermore, a particular arrangement of windows can be stored even
when a terminal is closed. This has a number of advantages:
1.  It allows a user to arrange windows in a way that works well for a
    particular task. As an example, a user may have a setup involving
    1.  a window open in which they are running vim to edit their code
    1.  a separate window for compiling their code
    1.  another in which to manage git
    1.  and another window with various splits to explore the various
        directories in which the relevant data are stored.
1.  When working on a remote server through ssh, a user can make only one
    connection and then work as though in several windows, which makes
    workflows more natural.
1.  It allows a user to more easily organize the elements of the system they
    have to keep track of.
1.  It allows for easy separation of workflows on separate projects, allowing
    for switching between them with minimal overhead.

### Basic Usage
tmux is extremely powerful and complex. However, just to scratch the surface,
here are some very useful commands with which to get started. In the following
commands, a combination of keys followed by a comma, and then another
combination means that first the keys before the comma should be pressed
together, then the sequence of keys after the comma.
*   `tmux`: start a new tmux session
*   `tmux new -s <name>`: start a new tmux session named "name"
*   `ctrl+b, d`: detach from the current tmux session
*   `tmux attach`: reconnect to the most recent tmux session which was detached
    from
When in a tmux session:
*   Windows:
  *   `ctrl+b, c`: create a new window
  *   `ctrl+b, x`: kill the current window
  *   `ctrl+b, <number>`: jump to window number <number> (current windows are
      displayed at the bottom of the screen)
*   Splits:
  *   `ctrl+b, %`: create a new vertical split
  *   `ctrl+b, "`: create a new horizontal split
  *   `ctrl+b, <arrow key>`: jump to the split in the direction of the arrow
      key hit
*   Sessions:
  *   `ctrl+b, w`: open a view in which windows and sessions can be swapped
      between. Use arrow keys to navigate to the correct session or window,
      and hit enter to enter it
*   `ctrl+d`: kill the current window/split (this is not a tmux-specific
    command, but will usually kill whatever terminal it is entered in to
