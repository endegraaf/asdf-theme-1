# asdf-theme-1
A small collection of Oomox based themes for Gnome. These themes were created by me because I really wanted a desktop experience which is easy on the eyes while maintaining enough contrast for proper visibility of window controls. 

The following themes are put in this repo:
- oomox-asdf-theme-1
- oomox-asdf-theme-darkblue-gradient
- oomox-asdf-theme-darkblue-flat

The rest of Gnome (shell, icons, etc) is left to defaults. 

There is one manual step you need to do because there are some window resize issues with the default generated themes. That is create (or append) to `~/.config/gtk-3.0/gtk.css` the following lines.

```
/*@define-color decoration_border_color #E6A531;*/
@define-color decoration_border_color_unfocused #0E0021;

/* focused window */
decoration {
    border: 1px solid @decoration_border_color;
    /* switch colors smoothly with a transition animation */
    transition: border-color ease-in 0.2s, background-color ease-in 0.2s;
}

/* unfocused window */
decoration:backdrop {
    border-color: @decoration_border_color_unfocused;
    background-color: @decoration_border_color_unfocused;
}

/* focused window (server-side rendering hack) */
.ssd .titlebar {
    border: 2px solid @decoration_border_color;
    border-bottom: none;

    /* transition animation does not seem to work with server-side rendering */
    /* transition: border-color ease-in 0.2s; */
}

/* unfocused window (server-side rendering hack) */
.ssd .titlebar:backdrop {
    border-color: @decoration_border_color_unfocused;
}

/* remove borders of maximized windows */
.maximized decoration,
.ssd.maximized .titlebar {
    border: none
}
```
