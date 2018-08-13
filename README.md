## What is in this repository?

This is a set of scripts used to support automation of Debian Unstable clang
builds, as in [irill8.siege.inria.fr](https://irill8.siege.inria.fr).

## How to use these scripts?

These scripts are supposed to be used with an [Open Build Service
(OBS)](https://openbuildservice.org) instance configured to build
Debian Unstable packages substituting GCC binaries for Clang ones.

To do so, you will also need to build the [obs-service-clang-build
package](https://github.com/athos-ribeiro/obs-service-clang-build).

First, you must have a dedicated mail server to receive emails from the
[debian-devel-changes](https://lists.debian.org/debian-devel-changes/) mailing
list. Then, configure the your credentials in the `check_new_uploads` script.
Intall both scripts available in this repository (with execution permissions)
in a directory mapped by your `$PATH` env variable, such as `/usr/local/bin`.
Then add call to `check_new_uploads` to your `crontab`.

`check_new_uploads` will trigger new Debian sid builds with clang whenever new
package uploads get approved in Debian unstable.

## TODO

`check_new_uploads` script is lightly based on the
[debian-devel-changes-bot](https://github.com/sebastinas/debian-devel-changes-bot).
We should allow the script to fetch emails from a self hosted mail server, as
the changes-bot does.

# Licence

obs-trigger-sid-builds
Copyright (C) 2018  Athos Ribeiro

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
