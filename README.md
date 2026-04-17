# chan-sccp

This repository contains the working chan-sccp driver for Cisco SCCP phones on Asterisk.

It is a compact fork-focused README with the basics only: build, install, and use.

## What this project is for

- Cisco SCCP/Skinny phone support in Asterisk
- Device registration and call handling
- Provisioning support for SCCP-based phone setups

## Requirements

- A supported Asterisk build with headers and development files
- Build tools such as `gcc`, `make`, `autoconf`, and `libtool`
- XML and XSLT development libraries
- OpenSSL development libraries
- `gettext`

If your system uses a package manager, install the usual development packages first. Exact package names vary by Linux distribution.

## Build from source

```bash
git clone https://github.com/timspb/chan-sccp.git
cd chan-sccp
./tools/bootstrap.sh
./configure
make -j2
make install
make reload
```

If you are updating an existing checkout:

```bash
git pull
./tools/bootstrap.sh
./configure
make -j2
make install
make reload
```

## Notes

- This fork is intended for active development and practical use.
- Keep the README short and focused so users can get to build and install steps quickly.
- The original upstream project is still the canonical chan-sccp source line.

## Troubleshooting

- If `./configure` fails, make sure the development packages are installed.
- If the build cannot find Asterisk headers, install the matching Asterisk dev package for your version.
- If the driver does not load, check Asterisk module loading and log output first.

