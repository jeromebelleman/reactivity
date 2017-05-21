An rxvt-unicode Perl extension script for monitoring terminal activity,
opening buffers in Vim and changing font size on the fly.  The [rxvt-unicode
terminal emulator](http://software.schmorp.de/pkg/rxvt-unicode.html)
is a good, very configurable alternative to xterm or the GNOME Terminal,
available in all systems.

# Available Actions

`mon`

Lets you monitor a terminal, such that it rings the bell every time something
changes in it. This is particularly useful if you've configured rxvt-unicode
to set the [urgency hint](http://cern.ch/jbl/doc/multitasking#urgency-hints)
upon bell and e.g. make your window glow red.

`vim`

Opens the entire terminal buffer into Vim, so you can comfortably
page it, search it, reorganise and extract the data in it.

`smallerfont`, `largerfont` and `resetfont`

Respectively decreases, increases and resets the font size in the terminal.

# Installation

Drop the `reactivity` file into `~/.urxvt/ext/`. Before running `xrdb
~/.Xresources`, you'll need to add the following lines to `~/.Xresources`:

```
URxvt.perl-ext: reactivity
URxvt.keysym.M-m: perl:reactivity:mon
URxvt.keysym.M-v: perl:reactivity:vim
URxvt.keysym.M-0: perl:reactivity:resetfont
URxvt.keysym.M-0x002d: perl:reactivity:smallerfont
URxvt.keysym.M-0x003d: perl:reactivity:largerfont
```

Writing [Perl extensions for rxvt-unicode](http://cern.ch/jbl/doc/urxvt)
is a great way to tailor it to suit your needs.
