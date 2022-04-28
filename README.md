# one-way-ssl

This APi contains the code for one way ssl and also explais how we use DB connetor in mule

- use this url (http://localhost:8081/api/clientapp) to call the client API (i.e my-db-pocFlow). which will call the server (i.e db-main-flow-server)


-The comman used in creation of client truststore and server key store

    generate server keystore
-keytool -genkey -alias mule-server -keysize 2048 -keyalg RSA -keystore server-keystore.jks


    Export the Public Certificate from server Keystore
-keytool -export -alias mule-server -keystore server-keystore.jks -file server_public.crt


    Importing server Public Certificatre Ito client Truststore
-keytool -import -alias mule-client-public -keystore client-truststore.jks -file server_public.crt
