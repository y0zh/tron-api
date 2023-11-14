# TRON API
A PHP API for interacting with the Tron Protocol

## Install

```bash
> composer require y0zh/tron-api --ignore-platform-reqs
```
## Requirements

The following versions of PHP are supported by this version.

* PHP 7.4

## Example Usage

```php
use y0zh\TronAPI\Tron;

$fullNode = new \y0zh\TronAPI\Provider\HttpProvider('https://api.trongrid.io');
$solidityNode = new \y0zh\TronAPI\Provider\HttpProvider('https://api.trongrid.io');
$eventServer = new \y0zh\TronAPI\Provider\HttpProvider('https://api.trongrid.io');

try {
    $tron = new \y0zh\TronAPI\Tron($fullNode, $solidityNode, $eventServer);
}
catch (\y0zh\TronAPI\Exception\TronException $e) {
    exit($e->getMessage());
}


$this->setAddress('..');
//Balance
$tron->getBalance(null, true);

// Transfer Trx
var_dump($tron->send('to', 1.5));

//Generate Address
var_dump($tron->createAccount());

//Get Last Blocks
var_dump($tron->getLatestBlocks(2));

//Change account name (only once)
var_dump($tron->changeAccountName('address', 'NewName'));


// Contract
$tron->contract('Contract Address');



```

## Testing

``` bash
$ vendor/bin/phpunit

