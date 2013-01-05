# guzzle-eway

A PHP 5.3+ Guzzle client for interacting with the Eway Direct Transaction API.

## Installation

Add this to your composer.json by running
`composer.phar require jwpage/guzzle-eway`.

## Usage

### Create API client

    $client = \Jwpage\Clickatell\ClickatellClient::factory();

### Send Payment

    $response = $client->getCommand('SendPayment', array(
        'customerID'      => '87654321',                                   
        'totalAmount'     => '10',                                         
        'cardHoldersName' => 'Foo Bar',                                    
        'cardNumber'      => '4444333322221111',                           
        'cardExpiryMonth' => '06',                                         
        'cardExpiryYear'  => '20',                                         
        'CVN'
    ))->execute();
    $response['trxnStatus']; // true
    $response['trxnError']['code']; // 10

## Running Tests

First, install PHPUnit with `composer.phar install --dev`, then run
`./vendor/bin/phpunit`.

## More Reading

* [guzzlephp.org: Consuming web services using web service clients](http://guzzlephp.org/tour/using_services.html)
* [eway.com.au: Response Codes](http://www.eway.com.au/developers/resources/response-codes)
* [eway.com.au: Direct Payments Sandbox](http://www.eway.com.au/developers/sandbox/direct-payments)
* [eway.com.au: Direct Payments Documentation](http://www.eway.com.au/developers/api/direct-payments)