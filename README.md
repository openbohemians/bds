# Base Directory Standards

The purpose of this project is to take the [XDG Base Directory Standard](http://standards.freedesktop.org/basedir-spec/latest/)
and [XDG User Directory Standard](http://www.freedesktop.org/wiki/Software/xdg-user-dirs) (collectively *XDG*),
as a starting point for a universal standard suitable for inclusion in the FHS.

## CONSIDERATIONS

### Fixed HOME Directories

Should the HOME directories remain environment variables rather
than using a stricter fixed convention? In other words, make
`~/.config` ALWAYS the user's configuration directory. The home
directories can be "reconfigured" instead via symlinks, if
so desired.

### Generalized .local

The `~/.local` directory that is part of the `$XDG_DATA_HOME`
default path should be made an explicit part of the standard.
In the Ruby XDG library this has been labeled `$XDG_RESOURCE_HOME`.
This directory is simply the per-user equivalent of the
system wide `/usr/local` directory.

### CONFIG Directories Default

For a universal standard, the current default path in `$XDG_CONFIG_DIRS`
should change from `/etc/xdg` to `/etc`.

### Removal of XDG Prefix

In the end, the removal of the `XDG` prefix may be warranted. Perhaps
replace by a more general term, or none at all.

### Equivalent for /var.

XDG lacks a corresponding directory for `/var`, although the latest version
provides `$XDG_RUNTIME_DIR` which is equivalent to `/var/run`.

This might be called `$XDG_VARIABLE_DIR`. Though referring to the first
issue above it may be a static `~/.variable`.

