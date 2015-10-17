package-switch
==============
[![Build Status](https://travis-ci.org/deprint/package-switch.svg)](https://travis-ci.org/deprint/package-switch) [![Dependency Status](https://david-dm.org/deprint/package-switch.svg)](https://david-dm.org/deprint/package-switch) [![apm](https://img.shields.io/apm/dm/package-switch.svg)](https://github.com/deprint/package-switch) [![apm](https://img.shields.io/apm/v/package-switch.svg)](https://github.com/deprint/package-switch)

## Easy package activation/deactivation
![package-switch-2](https://cloud.githubusercontent.com/assets/7817714/8269467/947642ce-17a9-11e5-8602-3a1de749edd1.png)

## Features
* Enable/disable packages without having to navigate settings-view
* Put multiple packages into `Bundles` to enable/disable them all at once
* Store local bundles in `.package-switch.cson` files
* Auto-execute local bundle if only one project is active
* Save and restore package states to save start-up time

## Usage
### Create a Bundle
1. Run `package-switch:create`
2. Each package has one of three "actions" (Select a package and press `Enter` to cycle through them):
  * Ignored (`/`) packages do not change when a bundle is executed
  * Added (`+`) packages will be enabled
  * Removed (`-`) packages will be disabled
![package-switch-create](https://cloud.githubusercontent.com/assets/7817714/8269547/deb667ca-17ad-11e5-9124-b5c3a4f42e74.png)
3. Press `Escape` once you've finished your list ( to abort: Press `Escape` twice )
4. A new dialog box will open where you enter the name of your bundle
![package-switch-name](https://cloud.githubusercontent.com/assets/7817714/8269546/d4a422ae-17ad-11e5-8384-8a9b72a9fd92.png)
5. Press `Enter` to create the bundle

### Execute a Bundle/Package
1. Run `package-switch:start-packages` or `package-switch:stop-packages`
2. Select the Bundle/Package
  * Added (`+`) packages will be enabled
  * Removed (`-`) packages will be disabled
  * `package-switch:stop-packages` does the opposite of `package-switch:start-packages`

### "Auto-enable" packages
To auto-enable packages you have to create a local configuration file called `.package-switch.cson` in your project's root folder.
This config file can store one bundle that will be executed when Atom starts in the project folder.

### "Auto-disable" packages
You may want to enable as few packages at startup as possible in order to reduce Atom's startup time.

1. Disable all packages that you do <b>not</b> want to activate when Atom starts
2. Go to package-switch settings
3. Enable "Save and restore packages"
4. The "Save Data" field should now contain a list with all currently disabled packages

When you now deactivate this package (e.g. by closing Atom) the configuration in "Save Data" will be loaded and when you start Atom these packages will be disabled.

## Debugging
Global bundles are stored in `~/.atom/package-switch.bundles` or your OS-equivalent.
Include this file in bug reports if you think the bug is in this file.
Local configuration files can be opened as a text editor by right-clicking the file in tree-view and clicking on `Open as Text`.

## Roadmap
* Bug fixes, etc.

## Contributing
* Let me know if you encounter any bugs.
* Feature requests are always welcome.
