# Patches for SDL2_net on SerenityOS

## `0001-Undefine-SIOCGIFCONF-on-serenity.patch`

Undefine 'SIOCGIFCONF' on serenity

FIXME: We don't know why yet.

## `0002-Include-sys-select.h.patch`

Include sys/select.h


## `0003-libtool-Enable-shared-library-support-for-SerenityOS.patch`

libtool: Enable shared library support for SerenityOS

For some odd reason, libtool handles the configuration for shared
libraries entirely statically and in its configure script. If no
shared library support is "present", building shared libraries is
disabled entirely.

Fix that by just adding the appropriate configuration options for
`serenity`. This allows us to finally create dynamic libraries
automatically using libtool, without having to manually link the
static library into a shared library.

