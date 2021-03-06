# macOS.config
How I configure new macOS workstations.

Since my work computers are also managed by an MDM (Jamf Pro), not all steps are applicable on such machines and there are different load sets for each. 

## Initial System Configuration
* Enable FileVault
	* Work
		* Enable per employer policy.
	* Home
	    * Do not escrow key with iCloud
	    * Save Key to 1Password
* Enable iCloud
	* Enable Document & Data Sync
* Log into MAS


* Install Xcode from MAS
* Install the latest [JDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html)

## Homebrew Configuration
Homebrew Installs most of the CLI, Direct Download & MAS Applications that I use. License and registration details are stored in 1Password, which is synced via iCloud and installed via Homebrew Bundler.

* Configure Xcode
    * `xcode-select --install`
    * `sudo xcodebuild -license`
* Install ["Home brew"](http://brew.sh) from source   
		* `sudo mkdir -p /usr/local/Homebrew && sudo chown nova486 /usr/local/Homebrew/`
		* `git clone git@github.com:Homebrew/brew.git /usr/local/Homebrew`
* Download this repository
    * `git clone https://github.com/uisge-beatha/macOS.config.git ~/Programming/macOS.config`
    * `~/Programming/macOS.config` will be the base directory from now on
* Primary Homebrew Bundler Installation
    * This will install universal Applications as defined in `~/Programming/macOS.config/Brewfile`
    * `cd ~/Programming/macOS.config`
    * `brew bundle`
        * If `brew bundle` did not automatically install Bundler
            * `cd ~/Programming/macOS.config`
            * `brew tap Homebrew/bundle`
            * `brew bundle`
    * Enable Primary Homebrew Bundler Services
        * `brew services start clipper`
        * `brew services start dbus`


## Apps installed directly from the internet:
* TextExpander https://smilesoftware.com/textexpander/download_thanks.html?url=http://cdn.smilesoftware.com/TextExpander_4.3.7.zip


* CloudApp
* Rocket http://matthewpalmer.net/rocket
* Sketch https://www.sketchapp.com
* Sync https://sync.com
* zsh https://github.com/robbyrussell/oh-my-zsh (.zshenv and .zshrc are in 1Password)
* GitHub Mac Credential Helper https://help.github.com/articles/caching-your-github-password-in-git/


* `/etc/hosts` file from http://winhelp2002.mvps.org/hosts.htm
* MacDown http://macdown.uranusjr.com
* Follow instructions on gpg-agent https://blog.erincall.com/p/signing-your-git-commits-with-gpg
* Install GPG Suite https://gpgtools.org 
* GitHub Clippers: https://github.com/orta/github-clippers

## Other Customizations

* Custom Safari Stylesheet in Sync
* Turn on zoom in Accessibility settings
* `git config --global push.default simple`
* `git config --global user.name "Ash Furrow"`
* `git config --global user.email ash@ashfurrow.com`
* `brew install trash` + alias https://twitter.com/kattrali/status/662052949326098432
* `defaults -currentHost write com.apple.ImageCapture disableHotPlug -bool YES`
* Always expand save file dialogue box `defaults write -g NSNavPanelExpandedStateForSaveMode -boolean true`
* http://merowing.info/2015/12/little-things-that-can-make-your-life-easier-in-2016/
* Import GPG key from 1Password
* Untrust certificate: https://blog.filippo.io/untrusting-an-intermediate-ca-on-os-x/ 
* VSCode https://code.visualstudio.com (+add symlinks to config files in Sync folder)
* Dark mode on menu bar
* Dock on right, auto-hide on
* Hide Desktop icons: `defaults write com.apple.finder CreateDesktop false`
