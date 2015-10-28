# Keep Calm and Trust No One: Protecting data with end-to-end encryption

by Joe Steinbring (@steinbring)

The slides and the code are tweeted out. 

Security is hard. 

Prevent it - Restrict physical access and reduce attack surface.

Shout out to Let's Encrypt

"Trust no one" security
* The user applies encrytion
* The server doesn't have the keys
* The server offers no password recovery options

A way that you can do that is use symmetric cryptography.

But someone could get to that key and decrypt everything. That's where asymmetric cryptography comes in. 

Public and private keys are used, PGP style.

## OpenPGP.JS

This is a JavaScript impementation of OpenPGP. It offers digital signatures, encryption, decryption and radix-64 conversion. This is promise based!

Some core methods
* `openpgp.generateKeyPair()` - need a userId, a password and a bit length
* `openpgp.encryptMessage()` - needs the public key object and the message
* `openpgp.decryptMessage()` - needs the private key and the encrypted message

## Live Demo

[OpenPGP.JS demo #1](http://www.steinbring.net/experiments/demo1.html)
[OpenPGP.JS demo #2](http://www.steinbring.net/experiments/demo2.html)

His demo uses Firebase!

The NSA cc's themselves. 
Enter user id, password, generate keys, publish public key and use it to send messages and decrypt them on the other end. 

## Potential pitfalls

There is *still* no excuse not to use SSL. This will prevent MITM kind of attacks. 
Signed browser extension is one way of dealing with this. Adding all of this information to a browser extension, you can assure that someone hasn't tampered with it. 

Might not want to encrypt everything though since this operation isn't without a price. 

## In the future

There will be a Web Cryptography API at some point but it is still a very fluid product.

OpenPGP is set up in a way that it will use the web crytography library when available. And it already uses the CPRNG out of the web cryptography API. 

Web cryptography methods
* `generateKey()`
* `importKey()`
* `exportKey()`
* `encrypt()`
* `decrypt()`
* `wrapKey()`
* `unwrapKey()`

[Web Cryptography demo](http://www.steinbring.net/experiments/demo3.html)

There is an info box that tells you more about the algorithm being used. 

## Questions

People don't userstand how encryption works. Can you encrypt the ciphertext to make it more secure? #Encryptception

Yay for public key parties! I should plan one. You can share public keys using web-based tools. 

