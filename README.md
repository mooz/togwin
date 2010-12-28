# Togwin

Show / Hide certain window (application) by pressing an key.

## Installation

If you are using Ubuntu, use apt-get to install [xdotool][xdotool].

    $ sudo apt-get install xdotool

Then, place `togwin` to certain directory in the `PATH`.

For example,

    $ sudo mv togwin /usr/local/bin

## Usage

    $ togwin
    Usage: /usr/local/bin/togwin [--class CLASS] [--title|--name NAME] [--action ACTION]
    Toggle focus status of certain window.
    
      CLASS    WM_CLASS of the window
      NAME     WM_NAME of the window
      ACTION   command which is executed when window is not found
    
    Use 'xprop WM_CLASS WM_NAME' to investigate the condition

Make command by using `togwin`. Then, bind it to the certain key in your window manager e.g. `Compiz`, `Metacity`, `Awesome` and `xmonad`.

## Examples

### Gnome-Terminal

Save the following script as `toggle-gnome-terminal`.

    #!/bin/sh
    
    togwin --class gnome-terminal --action gnome-terminal

### Gnome-Dictionary

Same as above.

    #!/bin/sh
    
    togwin --class gnome-dictionary --action gnome-dictionary

## Investigating class and names of window

Use `xprop WM_CLASS WM_NAME` to investigate the value of `--class` and `--name`.

    $ xprop WM_CLASS WM_NAME

[xdotool]: http://www.semicomplete.com/projects/xdotool/
