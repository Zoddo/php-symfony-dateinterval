DateInterval Bundle
===================

A Symfony bundle for the DateInterval library for Doctrine.

Summary
-------

The bundle will automatically

- register the `dateinterval` Doctrine mapping type
- add the `DATE_INTERVAL` DQL function

to the default entity manager (`doctrine.orm.entity_manager`).

Installation
------------

Add it to your list of Composer dependencies:

```sh
$ composer require zoddo/dateinterval-bundle=1.* herrera-io/doctrine-dateinterval=dev-master@dev
```

Add it to your `app/AppKernel.php` file:

```php
<?php

public function registerBundles()
{
    $bundles = array(
        // ... snip ...
        new Herrera\Symfony\DateInterval\DateIntervalBundle()
        // ... snip ...
    );
}
```

Usage
-----

### In your entities

```php
<?php

class MyEntity
{
    /**
     * @ORM\Column(type="dateinterval")
     */
    private $interval;
}
```

### In your queries

```sql
SELECT j FROM Jobs j WHERE j.interval < DATE_INTERVAL('PT1H')
```
