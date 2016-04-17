#### Version 0.0.0 (2016 April 00)

Initial development.

Forked from `iohyve` at 0.7.5 "Tennessee Cherry Moonshine Edition" release at commit [2ff5b50](https://github.com/pr1ntf/iohyve/commit/2ff5b50d8cda61a8364bd79319152142ac1b4c33).

Changed command from `iohyve` to `chyves`. It rhymes with the original project and creating a memorable logo is in the works.

Created new document structure and folder. Root folder contains documents about the project. The installed files are now in their respective places `sbin/`, `etc/rc.d/`, and `man/man8`

Changes other internal references to `iohyve` to `chyves`. For example, the VMM names now reference `chy-$guest`.

Fixed various typos in man page.

Created a new dataset to house all the guests under `$pool/chyves/guests/$guest`

Created a dataset, `$pool/chyves/.defaults`, which is referenced to build new guests instead of hard references. Might use for other uses besides guest creation.

Rewrote `chyves info()` to use flags for verbosity. See man page for available flags to use.

Added ability to specify UUID for guest. This is mostly helpful for Windows guests in regards to their licensing activation, however other use cases exist. UUID is generated on creation by /bin/uuidgen.

Additional kernel modules loaded with `chyves setup kmod=1` for networking taps and bridges. Creation of bridges and taps would fail without these modules.