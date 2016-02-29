# Bootstrap-ColorPicker Bundle for Symfony2

## Current Version

[Bootstrap Colorpicker 2.3](https://mjolnic.com/bootstrap-colorpicker/)

## Installation

### From the commandline

```
$ php composer.phar require jimigrunge/bootstrap-colorpicker-bundle
```

### OR configure it manually 

####Add bundle to your composer.json file

```
{
    "require": {
        // ...
        "jimigrunge/bootstrap-colorpicker-bundle": "2.3"
    }
}
```

#### Run commanline installer

```
$ php composer.phar update jimigrunge/bootstrap-colorpicker-bundle
```

### Add bundle to your application kernel (app/AppKernel.php)

```
public function registerBundles()
{
    $bundles = array(
        // ...
        new JimiGrunge\BootstrapColorPickerBundle\BootstrapColorPickerBundle(),
        // ...
    );
}
```

### Install assets

Given your server's public directory is named "web", install the public vendor resources

```
$ php bin/console assets:install web
```

Optionally, use the --symlink attribute to create links rather than copies of the resources

```
$ php bin/console assets:install --symlink web
```

## Usage

Once all the resources are in place you can edit any of your twig views or layouts to include the bootstrap-colorpicker
javascript files.

Note: bootstrap-colorpicker requires the jQuery library.

```
{% block javascripts %}
    <script src="//code.jquery.com/jquery-2.2.1.min.js"></script>
    {% javascripts
        ...
        '@BootstrapColorPickerBundle/Resources/public/js/bootstrap-colorpicker.min.js'
        ...
        %}
        <script src="{{ asset_url }}"></script>
    {% endjavascripts %}
{% endblock %}
```

Then you will want to load the css resources so your select elements look nice:

```
{% block stylesheets %}
    {% stylesheets filter='cssrewrite'
      ...
      'bundles/bootstrapcolorpicker/css/bootstrap-colorpicker.min.css'
      ...
    %}
        <link rel="stylesheet" href="{{ asset_url }}" />
    {% endstylesheets %}
{% endblock %}
```

### Assetic 

Dump bundled files to the filesystem.

```
$ php bin/console assetic:dump
```

## Licenses

I do not own bootstrap-colorpicker files at all, I'm just providing a Bundle package to easy-install them all.
Refer to the source code of the included files from Select2 for license information.

## References

1. https://mjolnic.com/bootstrap-colorpicker/
2. http://symfony.com