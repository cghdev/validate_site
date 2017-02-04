# validate_site
Bash script to x509 certificate status and chain on a server.


Example:
```
$ ./validate_site.sh github.com --crl
+++++++++++++++++++++++++++++++
NO OCSP Stapling detected
+++++++++++++++++++++++++++++++
[1]
Subject: businessCategory=Private Organization/1.3.6.1.4.1.311.60.2.1.3=US/1.3.6.1.4.1.311.60.2.1.2=Delaware/serialNumber=5157550/street=88 Colin P Kelly, Jr Street/postalCode=94107, C=US, ST=California, L=San Francisco, O=GitHub, Inc., CN=github.com
Issuer: C=US, O=DigiCert Inc, OU=www.digicert.com, CN=DigiCert SHA2 Extended Validation Server CA
Serial: 0BFDB4090AD7B5E640C30B16C9529A27
Signature Algorithm:  sha256WithRSAEncryption
Alternative Names: github.com www.github.com
        Not Before: Mar 10 00:00:00 2016 GMT
        Not After: May 17 12:00:00 2018 GMT

OCSP check:
WARNING: no nonce in response
Response Verify Failure
1995490512:error:27069076:OCSP routines:OCSP_basic_verify:signer certificate not found:ocsp_vfy.c:92:
0x0BFDB4090AD7B5E640C30B16C9529A27: good
        This Update: Feb  4 15:30:00 2017 GMT
        Next Update: Feb 11 14:45:00 2017 GMT

CRL check
    CDP: http://crl3.digicert.com/sha2-ev-server-g1.crl
        Last Update: Feb  4 17:03:13 2017 GMT
        Next Update: Feb 11 17:00:00 2017 GMT
        Cert status: OK

#########################
[2]
Subject: C=US, O=DigiCert Inc, OU=www.digicert.com, CN=DigiCert SHA2 Extended Validation Server CA
Issuer: C=US, O=DigiCert Inc, OU=www.digicert.com, CN=DigiCert High Assurance EV Root CA
Serial: 0C79A944B08C11952092615FE26B1D83
Signature Algorithm:  sha256WithRSAEncryption
        Not Before: Oct 22 12:00:00 2013 GMT
        Not After: Oct 22 12:00:00 2028 GMT

Certificate has AIA extension but could not find issuer's certificate. Skipping OCSP validation.

CRL check
    CDP: http://crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl
        Last Update: Feb  1 21:00:00 2017 GMT
        Next Update: Feb 22 21:00:00 2017 GMT
        Cert status: OK

#########################
```
