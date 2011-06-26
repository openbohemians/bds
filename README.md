# Base Directory Standards

The puropose of this project is to take the XDG Base
Directory Standard[1] and XDG User Directory Standard[2] 
(collectively *XDG*), as a starting point for a 
universal stanadrd suiteable for inclusion in the FHS.

[1] http://standards.freedesktop.org/basedir-spec/latest/
[2] http://www.freedesktop.org/wiki/Software/xdg-user-dirs


## Considertations

### Fixed HOME Directories

Should the HOME directories remain environment variables rather
than using a stricter fixed convention? In other words, make
`~/.config` ALWAYS the user's configuration directory. The home
directories can be "reconfigured" instead via symlinks, if
so desired.

### Generlized .local

The `~/.local` directory that is part of the $XDG_DATA_HOME
default path should be made an explict part of the standard.
In the Ruby XDG library this has been labled $XDG_RESOURCE_HOME.
This directory is simply the per-user equivalent of the
sytem wide `/usr/local` directory.

### CONFIG Directories Default

For a univeral standard, the current default path in $XDG_CONFIG_DIRS
should change from `/etc/xdg` to `/etc`.

### Removal of XDG Prefix

In the end, the removal of the XDG prefix may be warrented. Perhaps
replace by a more general term, or none at all.

