A really simple MessageBird SMS sender for PHP
=======================================================

What is this? <a name="what"></a>
-------------

A [PHP][] class, which is an implementation of the SMS API of [MessageBird](https://messagebird.com).

The implementation focus is to send SMS using Message Bird credentials (accessKey).
(You can get it by signing up to the [SMS API](https://developers.messagebird.com/api/sms-messaging/#send-outbound-sms).)

It is based on the [MessageBird PHP SDK](https://github.com/messagebird/php-rest-api) .

[PHP]: http://php.net/ "PHP is a popular general-purpose scripting language that is especially suited to web development."


Requirements
-----

- [Sign up](https://www.messagebird.com/en/signup) for a free MessageBird account
- Create a new access_key in the developers sections
- MessageBird API client for PHP requires [PHP 7.4 or higher](http://www.php.net/downloads.php) to use it.
  .

Installation <a name="installation"></a>
------------

Installation is recommended to be done via [composer][] by running:

	composer require karbura/sms-message-bird

Alternatively you can add the following to the `require` section in your `composer.json` manually:

```json
"karbura/sms-message-bird"
```

Run `composer update` afterwards.

[composer]: https://getcomposer.org/ "The PHP package manager"

Usage <a name="usage"></a>
-----

### In your PHP project

To send your sms, you'll need only two lines of code.

The first one is to set the accessKey and the originator
(the name of who send the message).

The next step is to call the `send()`-method to send the `message` to the `receivers`(recipients).

Here is an example:

```php
// Initialize the MessageBird
MessageBird::__construct("acessKey", "originator");

// Or create a component to use it

// send a message to a single receiver
$response = MessageBird::send(["+237653214587"], "My First SMS");

//Or

// set a list of receivers / recipients
$receivers = [
    "receiver1",
    "receiver2",
    "receiver3",
    ...
]

// and then make a single call to send
$response = MessageBird::send(["+237653214587"], "Send Many SMS");
```

Thank You for using this extension and if there is any problem, feel free to report it.