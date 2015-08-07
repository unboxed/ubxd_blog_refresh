---
layout: "blog"
date: "2015-01-26 01:50:00 UTC"
published: true
title: "Sending S/MIME encrypted emails with Action Mailer"
author: "Andrew White"

---

## Why send encrypted emails?

Most people are aware now that sending emails is somewhat akin to sending a postcard - pretty much everyone in the delivery chain is able to have a peek at your message. The only way to prevent this is to encrypt your message so that it appears as gobbledygook to anyone who tries to have a look. In addition to encrypting your email you'll also want to sign it as well to make sure that it hasn't been tampered with in transit.

The de-facto standard for encrypting and signing emails is [S/MIME][1], which has been around for well over a decade now and has wide support in email clients - the exception being the Google Mail web client but it does work fine when accessing Google Mail via IMAP with a client that supports S/MIME.

Support for S/MIME in Ruby comes as part of the OpenSSL standard library. It's very lightly documented but fortunately there's an [example of signing and encrypting][4] an email within the Ruby sample code.

## Getting started

The technique we will be using to send our encrypted emails is a rarely used feature in Action Mailer called [interceptors][2]. This feature allows you to hook into the email delivery before the email is sent, but after the email has been generated. The definition is straightforward with a single singleton method called `delivering_email`, e.g:

class MessageInterceptor def self.delivering\_email(message) message.to = ['test.user@ubxd.com'] end end

ActionMailer::Base.register\_interceptor(MessageInterceptor)

There are some nifty tricks that can be performed using this feature, one of which is inlining CSS for HTML emails - see [premailer-rails][3] for more information on how to do this.

## Implementing the delivering\_email method

Because of the way interceptors are implemented we have to mutate the message that's passed to our message, therefore we'll create an encrypted version of the message and copy the body back onto the original message along with certain headers. The basic outline looks like this:

require 'openssl'

class MessageEncryptor class > Notifications.send\_invoice(order).deliver

Assuming that all the certificates are in place you should receive an email in short order that is both signed and encrypted. If you're having problems it's almost certainly a mismatch with the certificates - either the trust level of a self-signed certificate isn't high enough or the common name doesn't match the email address.

Here's the complete class:

require 'openssl'

class MessageEncryptor class


