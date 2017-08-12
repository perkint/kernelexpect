Kernel Expect
=============

Kernel Expect (kernelexpect) is a small script that uses the Expect library to
automate Linux kernel configuration with dependency resolution.

The 'make nconfig' GUI configurator has dependency resolution but cannot be
automated at the command line.  There are some utilities that allow for
automated edits of the config (e.g.: scripts/config), but they do not do
dependency resolution.  This script tries to fill the gap...

The script can be used for a quick single config change:

```
  kernel-expect CONFIG_INTEL_MEI=n
```

Or...  It can be used to read a config file with many changes:

```
  vi /tmp/snippets_file

    # comments look like this...
    CONFIG_INTEL_MEI=n  # ... and this...

    # pick from a list...
    CC_STACKPROTECTOR_STRONG=choice

  kernel-expect -v -f /tmp/snippets_file
```

See also:
---------

* [scripted configuring of a linux kernel]
  (http://unix.stackexchange.com/questions/282946)

* [Non-interactive configuration of linux kernel]
  (https://unix.stackexchange.com/questions/19905)

* [Tor Perkins]
  (http://www.torp.com/resume/)

