---
permalink: update-an-existing-ssl-certificate/
audit_date: '2018-05-09'
title: Update an existing SSL certificate
type: article
created_date: '2011-08-16'
created_by: Chris Farmer
last_modified_date: '2018-05-09'
last_modified_by: Cat Lookabaugh
product: undefined
product_url: undefined
---

Updating your existing SSL certificate for a linux server is a quick process.
Whether your SSL certificate is expiring or you simply need to
change to a new SSL certificate, follow these instructions to
get your SSL updated and installed quickly.

**Attention MyRack users:** To update the SSL certificates for your
environment, follow the instructions in the [Reissuing your Rackspace SSL Certificates](https://community.rackspace.com/products/f/43/t/4478)
article posted in the Rackspace Support forum.

### Getting Started

In order to update or renew your SSL certificate, you need your
CSR. If you don't have your CSR saved, contact support to have a
new one generated. You can contact our **Fanatical Support**&reg; through a
ticket, live chat, or a phone call, and we can help you.

### Renewing Your Certificate

Next, you need to update or renew your SSL certificate. SSL
certificates are available from a number of third party sources. Some
recommended sellers are:

-  [RapidSSL](http://www.rapidssl.com)
-  [Geotrust](http://www.geotrust.com)
-  [Verisign](http://www.verisign.com)

Follow your vendor's SSL certificate renewal process. You might
need the following details:

-   **Server type**: For example, Apache 2.4.
-   **SSL type**: For example, OpenSSL (some vendors label this modSSL).
-   **CSR**

Once you have completed your certificate renewal, you're ready to install the new certificate.

### Installing the Certificate

In order to install your new SSL certificate, you need the following information:

-  Certificate
-  Private key
-  Intermediate certificate (Typically supplied in a separate file from the vendor)

To install the certificate, follow these steps:

1. Copy your renewed certificate, intermediate certificate bundle and key file into the directory 
   that you use to hold your certificates.

2. Open your webiste configuration file (for example, `httpd.conf` for Apache), and add or update the 
   following directives:

   - SSLCertificateFile: /path to your issued certificate
   - SSLCertificateKeyFile: /path to your key file
   - SSLCertificateChainFile: /path to your intermediate certificate
   
3. Restart your webserver.

### DNS Update

Because you are updating an existing SSL certificate, you don't need
to wait for propagation as you would when installing a new SSL certificate.

**NOTE**: Removing the SSL certificate from your site will change its IP address, which might require a DNS change.
