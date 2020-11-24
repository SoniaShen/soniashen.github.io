用openssl 和 keytool 生成 SSL证书
web link: https://www.jianshu.com/p/5cff7accfd78

使用keytool 生成证书
web link: https://www.cnblogs.com/littleatp/p/5922362.html

Simple way to generate a Subject Alternate Name (SAN) certificate:
web link: https://ultimatesecurity.pro/post/san-certificate/

使用openssl为ssl证书增加“使用者备用名称（DNS）
web link: https://blog.51cto.com/colinzhouyj/1566438

The Subject Alternative Name Field Explained:
web link: https://www.digicert.com/faq/subject-alternative-name.htm

KeyStore 和 TrustStore
web link: https://blog.csdn.net/andy_zhang2007/article/details/78805578

SSL Cerficate - No subject alternative names present
web link: https://stackoverflow.com/questions/20722406/ssl-cerficate-no-subject-alternative-names-present

Disable Certificate Validation in Java SSL Connections:
web link: https://nakov.com/blog/2009/07/16/disable-certificate-validation-in-java-ssl-connections/

How to fix the “java.security.cert.CertificateException: No subject alternative names present” error?
web link: https://stackoverflow.com/questions/19540289/how-to-fix-the-java-security-cert-certificateexception-no-subject-alternative
i.e. openssl s_client -showcerts -connect AAA.BBB.CCC.DDD:9443

How to resolve “unable to find valid certification path to requested target” error?
web link: https://jfrog.com/knowledge-base/how-to-resolve-unable-to-find-valid-certification-path-to-requested-target-error/


------------------------------------------------------------------------
keytool -selfcert -alias azure -genkey -dname "CN=localhost, OU=mp, O=CBC, L=Shanghai, ST=none, C=CN" -ext SAN=ip:127.0.0.1 -keystore azure.jks -storetype pkcs12 -keyalg RSA -storepass rootroot -keypass rootroot -validity 360 -keysize 2048
------------------------------------------------------------------------
Or:
------------------------------------------------------------------------
keytool -selfcert -alias fcmSimulator -genkey -keystore fcmSimulator.keystore -keyalg RSA -validity 1095
Enter keystore password:
Keystore password is too short - must be at least 6 characters
Enter keystore password:
Keystore password is too short - must be at least 6 characters
Enter keystore password:  fcmSimulator
Re-enter new password: fcmSimulator
What is your first and last name?
  [Unknown]:  Mac
What is the name of your organizational unit?
  [Unknown]:  Peng
What is the name of your organization?
  [Unknown]:  Ericsson
What is the name of your City or Locality?
  [Unknown]:  Kista
What is the name of your State or Province?
  [Unknown]:  SHanghai
What is the two-letter country code for this unit?
  [Unknown]:  cn
Is CN=Mac, OU=Peng, O=Ericsson, L=Kista, ST=SHanghai, C=cn correct?
  [no]:  yes

Enter key password for <fcmSimulator>
        (RETURN if same as keystore password):

------------------------------------------------------------------------

keytool -exportcert -alias bootstrap -keystore $KEYSTORE_DIR/keystore.pkcs12 -rfc -file $KEYSTORE_DIR/mmas.cer -noprompt -storepass rootroot
keytool -importcert -file $KEYSTORE_DIR/mmas.cer -alias jboss -keystore $KEYSTORE_DIR/tsTrustStore.pkcs12 -noprompt -storepass rootroot -storetype pkcs12





keytool -exportcert -alias azure -keystore azure.jks -rfc -file azure.cer -noprompt -storepass password


keytool -v -genkey -keyalg RSA -alias bootstrap -keystore $KEYSTORE_DIR/keystore.jks -dname "CN=127.0.0.1, OU=mp, O=CBC, L=Shanghai, ST=none, C=CN" -ext SAN=ip:127.0.0.1 -storepass rootroot -keypass rootroot -validity 360 -keysize 2048


keytool -v -genkey -keyalg RSA -alias bootstrap -keystore $KEYSTORE_DIR/keystore.jks -dname "CN=127.0.0.1, OU=mp, O=CBC, L=Shanghai, ST=none, C=CN" -ext SAN=ip:127.0.0.1 -storepass rootroot -keypass rootroot -validity 360 -keysize 2048




keytool -importcert -file $KEYSTORE_DIR/mmas.cer -alias jboss -keystore $KEYSTORE_DIR/tsTrustStore.pkcs12 -noprompt -storepass rootroot -storetype pkcs12


keytool -selfcert -alias azure -genkey -dname "CN=localhost, OU=mp, O=CBC, L=Shanghai, ST=none, C=CN" -ext SAN=ip:127.0.0.1 -keystore azure.jks -storetype pkcs12 -keyalg RSA -storepass rootroot -keypass rootroot -validity 360 -keysize 2048



----------------------------------------------------------------------
Generate rsa private key:
    openssl genrsa -out private.pem 2048

Generate public according private key:
    openssl rsa -in private.pem -outform PEM -pubout -out

Show modulus and exponent of public key:
    openssl rsa -pubin -in public.pem -noout -text



















