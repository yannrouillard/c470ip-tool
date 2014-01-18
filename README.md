c470ip-tool
===========

C470ip-tool is a simple tool that allows you to perform from the command line some operations on the Gigaset C470 IP phone.

Prerequisites
=============

You will need the following python modules to use c470ip-tool:
 * ```mechanize```: to be able to mimic a browser when accessing the C470 IP web inteface,
 * ```gdata```: to be able to access Google Contacts information.

Concerning ```gdata```, you will need to compile it by yourself to be able to include a required patch that add supports for [Google OAuth 2.0 for Device](https://developers.google.com/accounts/docs/OAuth2ForDevices).
The patch is available at that url: https://codereview.appspot.com/52810043/.


How to use it 
=============

So far the only really useful operation is the synchronisation of the address book with your Google Contacts information.
To use it you will first need to go to the [Google Developers Console](https://cloud.google.com/console/project), create a project name and then create a "Client ID for native application".

Once you have the client id and the client secret, you can simply synchronize your with the following command:
```
CLIENT_ID='YOUR_CLIENT_ID' CLIENT_SECRET='YOUR_CLIENT_SECRET' c470ip-tool google-sync --pin PIN http://C470IP_IP_ADDRESS/
```

where ``PIN``` is the four digit code required to access the C470IP web interface (it's 0000 by default).
