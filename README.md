
Des
===

Des source code for js,perl and php.


# Licensing and Usage

Several people have asked me about licensing issues, and whether it is possible to use this version of DES in a commercial or personal application. This page tries to answer that question, and also shows known places where this DES algorithm is being used.

# Licensing
The Javascript version of DES is based on a C version written and copyrighted by Eric Young as part of his SSL implementation. I went line by line through the C code, also following an in-depth description of the algorithm from another publication, and slowly built up the Javascript version. So as far as I am concerned the Javascript, Perl and PHP versions can be used in any way you would like, though I would like to be informed of any commercial usage. But I don't know if there are any other licensing implications. I would be very pleased if someone legally minded could [tell me](http://www.tero.co.uk/home/contact.php).

# About 
I only started doing this in August 2008 so it's not complete. Please [send me](http://www.tero.co.uk/home/contact.php) any other uses you find.

- [Encryptadoro] - a widget for the Mac OS X dashboard for encrypting passwords
- [Omerta] - for encrypting and decrypting messages
- [DES Password Pro] - for creating multiple user Javascript login forms
- [e-Will] - a safe way to send messages to friends in case something happens to you (added 31/8/2008)
- [Klepshydra] - Mac widget for encrypting messages (added 7/9/2009)
- [Joomla Encryption Configuration] - a Joomla extension for encrypting passwords and other data in your component (added 5/6/2010)

The project site: [http://www.tero.co.uk/des/usage.php](http://www.tero.co.uk/des/usage.php)

[Encryptadoro]: http://www.apple.com/downloads/dashboard/networking_security/encryptadoro.html
[Omerta]: http://midsummernightsdream.de/omerta/index_e.html
[DES Password Pro]: http://www.rustyspigot.com/webmasters/DESPasswordPro/
[e-Will]: http://e-will.appspot.com/
[Klepshydra]: http://klepshydra.blogspot.com/
[Joomla Encryption Configuration]: http://www.ratmilwebsolutions.com/downloads/encryption-configuration.html


# Usage
des (string key, string message, boolean encrypt, [integer mode, string iv, integer padding])
The des function accepts an 8 character string as the key (this is 64 bits, but the algorithm only uses 56) for normal DES or a 24 character string for triple DES, a message string, a boolean to say whether the data should be encrypted or decrypted, an optional mode (0 for ECB and 1 for CBC, ECB is the default), an optional 8 character string input vector (not used in ECB mode), and the type of padding (0 for null or zero bytes, 1 for PKCS7, 2 for spaces and 3 for no padding at all). It returns the cipher text as a string.

Here are several examples showing how it can be used:

    //encrypt using single DES (with an 8 byte key) in CBC mode
    //with the given input vector and PKCS7 padding
    des ("8bytekey", "This is the message.", 1, 1, "inputvec", 1);
    //encrypt using triple DES (with a 24 byte key) in ECB mode
    des ("this is a 24 byte key !!", "This is the message.", 1);
    //decrypt using single DES in ECB mode
    des ("8bytekey", "2384lf&*£90LSdsf", 0);

Source Code
There is no warranty for this code and I cannot be held responsible for any problems arising from using it (including those caused by bugs). It has been tested to see if it produces correct output, but has not been robustly tested on different browsers, processors, or with a wide range of keys and messages. Any modifications to this code must be posted on this site. If you find any errors, bugs, security holes, or have any questions or comments please email us.
