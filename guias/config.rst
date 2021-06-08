Configurar el Hyper-V para replicación
======================


Utilizaremos la siguiente premisa para la configuración de la replicación.

	nodo01.dominio.local - 192.168.1.20 - Primario donde estarán las VM

	nodo02.dominio.local - 192.168.1.21 - Secundario el cual recibirá la replica de las VM


Vamos a empezar en el **nodo02** abrimos el Hyper-V y lo vamos a configurar para que sea la Replica.


.. figure:: ../images/config/01.png

Como se vera, hay dos tipos de autenticación en Hyper-V: por Kerberos y por certificados HTTPS. Teniendo en cuenta que Kerberos está disponible solo en entornos de dominio, Como este laboratorio no esta en un dominio vamos por la opción de certificados.

.. figure:: ../images/config/02.png

Nos genera el siguiente error porque no tenemos certificado.

.. figure:: ../images/config/03.png

Vamos a proceder a crear los certificados y colocarlos en donde correspondan.

En el **nodo01** vamos a ejecutar en powershell los siguiente comandos::

	New-SelfSignedCertificate -DnsName “nodo01.dominio.local” -CertStoreLocation “cert:\LocalMachine\My” -TestRoot

	New-SelfSignedCertificate -DnsName “nodo02.dominio.local” -CertStoreLocation “cert:\LocalMachine\My” -TestRoot


.. figure:: ../images/config/04.png

Verificamos en el **mmc** los certificados creados.

.. figure:: ../images/config/05.png

Verificamos en el **mmc** el certificados Trusted Root Test.

.. figure:: ../images/config/06.png


En el **mmc** vamos a leer los dos (2) certificados y el certificaro Root Test que los firmo.

.. figure:: ../images/config/07.png

.. figure:: ../images/config/08.png

.. figure:: ../images/config/09.png

.. figure:: ../images/config/10.png

.. figure:: ../images/config/11.png


Se han configurado los certificados para el servidor principal, nodo01.dominio.local. El siguiente paso es exportar el certificado del servidor nodo02.dominio.local junto con el certificado Root Test CertReq e importarlos a servidor nodo02.dominio.local


.. figure:: ../images/config/12.png


.. figure:: ../images/config/13.png


.. figure:: ../images/config/14.png


.. figure:: ../images/config/15.png


.. figure:: ../images/config/16.png


.. figure:: ../images/config/17.png


.. figure:: ../images/config/18.png


.. figure:: ../images/config/19.png


.. figure:: ../images/config/20.png


Exportamos el certificado Root Test CertReq

.. figure:: ../images/config/21.png


.. figure:: ../images/config/22.png


.. figure:: ../images/config/23.png



.. figure:: ../images/config/24.png


.. figure:: ../images/config/25.png



.. figure:: ../images/config/26.png



.. figure:: ../images/config/27.png


Ahora los copiamos al nodo02.dominio.local

.. figure:: ../images/config/28.png


Nos genera el siguiente error

.. figure:: ../images/config/29.png

En ambos servidores debemos habilitar el **Advanced Sharing Setting** del network

.. figure:: ../images/config/30.png

.. figure:: ../images/config/31.png

Volvemos a probar


.. figure:: ../images/config/27.png


.. figure:: ../images/config/32.png


Ya tenemos los certificados copiados en el nodo02.dominio.local ahora los vamos a importar con la ayuda del mmc

.. figure:: ../images/config/33.png

.. figure:: ../images/config/34.png

.. figure:: ../images/config/35.png

.. figure:: ../images/config/36.png

.. figure:: ../images/config/37.png


.. figure:: ../images/config/38.png

.. figure:: ../images/config/39.png


.. figure:: ../images/config/40.png

Ahora importamos el Root Test 

.. figure:: ../images/config/41.png

.. figure:: ../images/config/42.png


.. figure:: ../images/config/43.png


.. figure:: ../images/config/44.png


.. figure:: ../images/config/45.png


.. figure:: ../images/config/46.png

.. figure:: ../images/config/47.png







