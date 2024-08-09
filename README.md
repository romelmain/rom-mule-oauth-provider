# rom-mule-oauth-provider

Esta Api es la encargada de generar y validar token

Necesita las librerias: mule-oauth2-provider-module y mule-objectstore-connector
las cuales ya estan definidas en el archivo pom.xml

La operación createClient es la que se encarga de crear el cliente para
posteriormente obtener el token

Una vez configurada, solo necesita egregar en los headers de entrada
los valores para client_id, client_secret, client_name

La operación token es la que entrega el token
solo se necesita especificar en los headers los mismos valores de 
client_id y client_secret usados en la operación anterior 
y grant_type debe ser igual a CLIENT_CREDENTIALS

Esta Api de ser desplegada en cloudhub y luego ejecutar /createClient y luego /token 
y guardar el token para su uso posterior

Por último, Agrega la política OAuth 2.0 Access Token Enforcement using Mule OAuth Provider
Asociada al Api rom-prueba-mulesoft-sys-api en Api Manager en donde se debe especificar el
Access Token validation endpoint url colocando la url del Api rom-mule-oauth-provider desplegada en cloudhub
