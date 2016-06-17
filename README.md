# Magento Composer Autoload

Complete and simple to install Composer autoloader to Magento

## Installation

### Using magento-composer-installer

To install this autoload using [magento-composer-installer](https://github.com/Cotya/magento-composer-installer) you need to follow these steps:

1. Create `composer.json` file (if it is not created already) and add extra parameters:
 - `magento-root-dir` - Magento document root Path to Magento root directory regarding to `composer.json` file.
 - `with-bootstrap-patch` - Prevent patching the `Mage.php` file.

For example, if your `composer.json` file is in Magento root directory, then the extra configuration should look like this:
 ```json
 "extra": {
     "magento-root-dir": ".",
     "with-bootstrap-patch": false
 }
 ```

 2. Add `magento-composer-installer` and `magento-composer-installer` to composer requirements:

 ```sh
 composer require magento-hackathon/magento-composer-installer
 composer require romantomchak/magento-composer-autoload
 ```

### Manual install

If you want to install composer autoload manually (without using magento-composer-installer), you only need to copy the `Autoload.php` file from this repository to `app/code/community/Varien` directory in your Magento installation.

## Configuration

This extension trying to locate the native composer autoloader which is located in `vendor` directory. The `vendor` directory may be in Magento root directory or Magento lib directory.
If you use the custom vendor directory, you need to specify the path to it by selecting one of two ways:
 - define `MAGE_VENDOR_ROOT` php constant with full path to the `vendor` directory (without a slash at the end)
 - set `MAGE_VENDOR_ROOT` environment variable with full path to the `vendor` directory (without a slash at the end)


Also you can specify the custom `name` for vendor directory by:
 - define `MAGE_VENDOR_DIR_NAME` php constant with `vendor` directory name
 - set `MAGE_VENDOR_DIR_NAME` environment variable with `vendor` directory name
