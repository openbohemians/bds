# B.D.S. - Base Directory Standard

The purpose of this project is to take the [XDG Base Directory Standard](http://standards.freedesktop.org/basedir-spec/latest/)
and [XDG User Directory Standard](http://www.freedesktop.org/wiki/Software/xdg-user-dirs) (collectively *XDG*),
as a starting point for a universal standard suitable for inclusion in the [File Hierarchy Standard](http://fhs.org).


## SPECIFICATION

### Home Directories

* `$HOME_ETC`
* `$HOME_USR`
* `$HOME_VAR`
* `$HOME_TMP`

The defaults for each respectively:

* `~/.etc` or `~/.config`
* `~/.usr` or `~/.local`
* `~/.var` or `~/.variable`
* `~/.tmp` or `~/.cache`

The later are for compatibility with XDG. (Note: `.variable` might be replaced with a more succinct name if a goof name can be determined.)

### System Directories

* `$DIRS_ETC`
* `$DIRS_USR`
* `$DIRS_VAR`
* `$DIRS_TMP`

The defaults for each respectively:

* `/etc`
* `/usr/local:/usr`
* `/var`
* `/tmp`

Notice we did not provide and equivalent for XDG's `$XDG_DATA_HOME` or `$XDG_DATA_DIRS`. In XDG the default home location points to `~/.local/share`. To access the same location via BDS use `$HOME_USR/share`. However, if deemed necessary, `$HOME_SHARE` and `$DIRS_SHARE` can be added.


## CONSIDERATIONS

### Local Equivalent for /var

Although the latest XDG standard provides for `$XDG_RUNTIME_DIR` which corresponds to `/var/run` in the FHS, XDG lacks any corresponding locals for `/var` itself. In BDS the equivalent to `/var` is supported by `$HOME_VAR` and `$DIRS_VAR` and defaults to the locations `~/.var` and `/var`, respectively.

### Generalized .local

The `~/.local` directory that is the prefix of the default `$XDG_DATA_HOME`
path is an explicit part of the BDS standard. (In the Ruby XDG library
this had been labeled `$XDG_RESOURCE_HOME`.) This directory is simply the per-user equivalent of the system wide `/usr/local` or `/usr` directory.

### CONFIG Directories Default

For a universal standard, the sub-directory path of `$XDG_CONFIG_DIRS`
should not be required. So instead of `/etc/xdg`, the default is `/etc`.

### Removal of XDG Prefix

By reversing the word order, no special prefix is needed for the environment variable names.

