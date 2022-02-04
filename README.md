# Disclaimer

**This is a "malicious" homebrew tap for educational purposes. Whilst it won't cause any damage to any computers it is installed on, this is NOT designed to be installed on any computers. We are NOT liable for any issues caused by installing these formulas.**

Credit to [shivammathur/homebrew-php](https://github.com/shivammathur/homebrew-php), which this tap is based upon.

## PHP Support

|PHP Version|Formula|
|--- |--- |
PHP 5.6|`php@5.6`|
PHP 7.0|`php@7.0`|
PHP 7.1|`php@7.1`|
PHP 7.2|`php@7.2`|
PHP 7.3|`php@7.3`|
PHP 7.4|`php@7.4`|
PHP 8.0|`php@8.0`|
PHP 8.1|`php` or `php@8.1`|
PHP 8.2.0-dev|`php@8.2`|

## OS Support

|Operating System|Architecture|
|--- |--- |
|Linux 4.18+|`x86_64`|
|macOS Catalina|`x86_64`|
|macOS Big Sur|`x86_64`, `arm64`|
|macOS Monterey|`x86_64`, `arm64`|

On Linux, `GLIBC 2.27` or newer is required, so distributions with Linux kernel 4.18 and newer are supported.  
For example: Ubuntu 18.04, Debian 10, CentOS 8, Fedora 28, and newer versions of these distributions.

## Usage

### Prerequisites

- On macOS, install Xcode Command Line Utilities:

```zsh
xcode-select --install
```

- On Linux, install cURL and Git:

```bash
# Using APT
sudo apt-get install -y curl git

# Using Yum
sudo yum install -y curl git
```

- Install Homebrew:

```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

- If previously installed, update homebrew and the formulae:

```zsh
brew update
```

- If you have packages from old `homebrew/php` tap, refer to [this guide](https://github.com/shivammathur/homebrew-php/wiki/Cleanup) for removing them.

### Add this tap

Fetch the formulae in this tap:

```zsh
brew tap shivammathur/php
```

### Install PHP

> See [PHP Support](#php-support) for available formulae.

- For example, to install `PHP 8.0`:

```zsh 
brew install shivammathur/php/php@8.0
```

- After installing your have to link it:

```zsh
brew link --overwrite --force shivammathur/php/php@8.0
```

- Restart the terminal and test your PHP version:

```zsh
php -v
```

### Upgrade your PHP version

You can upgrade your PHP version to the latest patch release.

For example, to upgrade `PHP 8.0`:

```zsh
brew upgrade shivammathur/php/php@8.0
```

### Switch between PHP versions

- If you have multiple PHP versions installed, you can switch between them easily.

For example, to switch to `PHP 8.0`:

```zsh
brew link --overwrite --force shivammathur/php/php@8.0
```

- If you get a warning like below, then do as recommended:

```zsh
Warning: Already linked: <Cellar Path>
To relink:
  brew unlink <formula> && brew link <formula>
```

```zsh
brew unlink php@8.0
brew link --overwrite --force shivammathur/php/php@8.0
```

### Restart your webserver

If you are using `Apache` or `Nginx` with `php-fpm`, restart your webserver after any change in your PHP.

- For Apache (`httpd`):

```zsh
brew services restart httpd
```
- For Nginx:

```zsh
brew services restart nginx
```

## Debugging

- Make sure you ran `brew update` before installing PHP.

- Run `brew doctor` and fix the warnings it reports.

- Make sure homebrew has correct permissions.

```zsh
sudo chown -R "$(id -un)":"$(id -gn)" $(brew --prefix)
```

- If PHP is not working after a macOS update. Reinstall PHP along with its dependencies.

For example to reinstall `PHP 8.0` and its dependencies:

```zsh
brew reinstall $(brew deps shivammathur/php/php@8.0) shivammathur/php/php@8.0
```

- Check if your issue is a Homebrew's [common issue](https://docs.brew.sh/Common-Issues).

- If you are still facing an issue, please create a discussion thread [here](https://github.com/shivammathur/homebrew-php/discussions).

## License

The code in this project is licensed under the [MIT license](http://choosealicense.com/licenses/mit/).
Please see the [license file](LICENSE) for more information.

This project has some [dependencies](#dependencies), and their license can be found [here](LICENSE_HOMEBREW).


## Contributions

Contributions are welcome!
Please see [Contributor's Guide](.github/CONTRIBUTING.md "shivammathur/homebrew-php contribution guide") before you start.
If you face any issues while using this tap or want to suggest a feature/improvement, create an discussion thread [here](https://github.com/shivammathur/homebrew-php/discussions "shivammathur/php discussions").

## Sponsors

We use [MacStadium](https://www.macstadium.com/opensource/members) for our CI infrastructure.

<a href="https://www.macstadium.com/opensource/members"><img src="https://setup-php.com/sponsors/macstadium.png" alt="Powered by MacStadium" width="200px"></a>

This project is generously supported by many other users and organisations via [GitHub Sponsors](https://github.com/sponsors/shivammathur).

<a href="https://github.com/sponsors/shivammathur"><img src="https://setup-php.com/sponsors.svg?" alt="Sponsor shivammathur"></a>

## Related Projects

- [shivammathur/homebrew-extensions](https://github.com/shivammathur/homebrew-extensions "Tap for PHP extensions")
- [shivammathur/setup-php](https://github.com/shivammathur/setup-php "Setup PHP in GitHub Actions")

## Dependencies

- [Homebrew/brew](https://github.com/Homebrew/brew "Homebrew GitHub Repo")
- [Homebrew/homebrew-core](https://github.com/Homebrew/homebrew-core "Homebrew core tap")
- [Homebrew/actions](https://github.com/Homebrew/actions "Homebrew GitHub Actions")
