[![version](https://img.shields.io/badge/version-1.0.0-green.svg?style=flat-square)](https://github.com/pierrechls/sf-standalone-bundle)

# sf-standalone-bundle

> An empty application in your Symfony2 bundle

Create an *empty application* in your *bundle* to *test* it (manually or automatically) outside of an actual application.

## :rocket: How to use it

#### Go to your bundle project

```bash
$ cd /path-to/the-bundle-project
```

#### Create a test folder

```bash
$ mkdir Tests
$ cd Tests
```

#### Clone the repo

```bash
$ git clone https://github.com/pierrechls/sf-standalone-bundle.git
```

#### Your bundle structure

Now your bundle structure should look something like this :

```bash
.
├── src/
│   └── AppBundle/
│
├── Tests/
│   ├── app/
│   │   ├── config/
│   │   │   ├─ config.yml
│   │   │   ├─ parameters.yml
│   │   │   └─ services.yml
│   │   ├── .htaccess
│   │   ├── AppCache.php
│   │   ├── AppKernel.php
│   │   ├── autoload.php
│   │   └── console.php
│
├── .gitignore
```

#### Update the composer.json file of your bundle

- Adding autoload configuration

```json
"autoload": {
    "psr-4": {
        "Acme\\StandaloneBundle\\": ""
    }
}
```

- Adding HttpKernel dependency in your `composer.json`

```json
"require": {
    "symfony/http-kernel": "~2.3"
}
```

#### Adding your bundle into the Kernel

- Open the file named `AppKernel.php` into the `app` folder

- Adding your bundle, for example :

```php
public function registerBundles()
{
    return array(
        // list of some bundles
        new AppBundle\AppBundle() // your bundle
    );
}
```

#### Configure

Adding your bundle configuration using `config.yml`, `parameters.yml` and `services.yml` files.

#### Run console

```bash
$ php Tests/app/console.php
```

#### Advice

- Ignore `Tests` folder by adding this line in your `.gitignore` bundle project :

```bash
Tests/
```

- For more informations you can check this [article](https://gnugat.github.io/2014/10/29/sf2-bundle-standalone.html)


## :raised_hands: Contribute

Contributing to sf-standalone-bundle it's a piece of :cake:. You have an idea about a new feature ? Fork the repo, do your stuff and open a [pull request](https://github.com/pierrechls/sf-standalone-bundle/compare) ! You can also report a problem or a suggestion by opening an [issue](https://github.com/pierrechls/sf-standalone-bundle/new).

## :tada: Credits

Project developed by [pierrechls](https://github.com/pierrechls/).
