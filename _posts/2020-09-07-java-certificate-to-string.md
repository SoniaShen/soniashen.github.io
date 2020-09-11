Write x509 certificate into PEM formatted string in java?
web link: https://stackoverflow.com/questions/3313020/write-x509-certificate-into-pem-formatted-string-in-java
i.e.
import org.apache.commons.codec.binary.Base64;
---
protected static String convertToPem(X509Certificate cert) throws CertificateEncodingException {
 Base64 encoder = new Base64(64);
 String cert_begin = "-----BEGIN CERTIFICATE-----\n";
 String end_cert = "-----END CERTIFICATE-----";

 byte[] derCert = cert.getEncoded();
 String pemCertPre = new String(encoder.encode(derCert));
 String pemCert = cert_begin + pemCertPre + end_cert;
 return pemCert;
}

 =====> =====> =====> =====> =====> =====>

























