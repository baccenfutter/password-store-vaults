# pass-vaults

An extension for the standard unix password manager:
[Password-Store](https://git.zx2c4.com/password-store)

This extension adds support for maintaining multiple separate password stores
under the same account.
It moves the location of the stores to sub-directories under ~/.password-vaults
and replaces ~/.password-store with a symbolic link pointing to the currently
active password store.
Several sub-commands are included, that allow the user to easily create
additional stores, maintain them and switch back and forth between them.

## Features

- support for managing multiple separate password-stores, called vaults
- vaults exist in distinct sub-directories of `~/.password-vaults/`
- the currently active vault is symlinked to `~/.password_store/`
- when activating another vault, the new vault is symlinked to
  `~/.password-store`
- easily create, list, rename and delete stores

## Dependencies

- This extension requires pass-v1.7.x or later.

## Installation

```bash
# The included Makefile will install the extension into the password
# store of the current user.
git clone https://github.com/baccenfutter/password-store-vaults
cd password-store-vaults
make install

# Extensions are only executed if the evironment variable
# PASSWORD_STORE_ENABLE_EXTENSIONS is set to 'true'.
export PASSWORD_STORE_ENABLE_EXTENSIONS=true
echo 'export PASSWORD_STORE_ENABLE_EXTENSIONS=true' >> ~/.bashrc

# Once the installation has been completed successfully, you can
# initialize the vaults by running:
pass vault init
```

## Configuration

- The default location of the standard password store can be overwritten with:
  `$PASSWORD_STORE_DIR`
- The default location of the password vaults can be overwritten with:
  `$PASSWORD_STORE_VAULT_DIR`

## Usage

Find usage information by executing: `pass vault help`

## License

GNU/GPL Version 2, June 1991

See: ***LICENSE*** file.
