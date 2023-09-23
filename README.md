#how to create a self signed certificate
How to Create a Self Signed Code Signing Certificate

You can create a self signed code signing certificate using OpenSSL. Or, for Windows 10 users, you can use PowerShell’s New-SelfSignedCertificate, an automated script that makes the job of creating such certificates easier for you. Just type in the command below to add your certificate to the certificate store:

$cert = New-SelfSignedCertificate -DNSName "www.domain.com" -CertStoreLocation Cert:\CurrentUser\My -Type CodeSigningCert -Subject “Example Code Signing Certificate”

# digital-sign
signtool sign /f "c:\codesigningcertificate\digicert_certificate\codesigningscertificate.pfx" /p “yourpasswordhere” /tr http://timestamp.digicert.com /td SHA256 /fd SHA256 "c:\codesigningcertificate\myexecutable.exe"

example:
signtool sign /f "E:\certificate\vaibhav-self-sign.pfx" /p "Type-your-password" /tr http://timestamp.digicert.com /td SHA256 /fd SHA256 "C:\turtle.exe"
