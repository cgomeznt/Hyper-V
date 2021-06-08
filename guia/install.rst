Instalar Hyper-V
================


Este laboratorio se realizo sobre el SO Microsoft Windows Server 2016 Datacenter. Tendremos dos (2) servidores

nodo01.dominio.local - 192.168.1.20
nodo02.dominio.local - 192.168.1.21

Las siguientes configuraciones se deben realizar en ambos Servidores.

**Habilitar Remote Desktop y permitir en el Firewall la conexión**

.. figure:: ../images/install/01.png

.. figure:: ../images/install/02.png



**Configuramos los nombres de los Servidores y el Workgroup**

.. figure:: ../images/install/03.png

.. figure:: ../images/install/04.png

Colocar Primary DNS Sufix

.. figure:: ../images/install/05.png

Reiniciamos el Servidor


Configurar el archivo hosts en ambos servidores.

.. figure:: ../images/install/06.png


**Habilitar el firewall el ICMP y hacer las pruebas de ping entre los servidores**

.. figure:: ../images/install/24.png

Hacer el ping desde los dos servidores 

.. figure:: ../images/install/25.png

.. figure:: ../images/install/26.png

Las siguientes configuraciones se deben realizar en ambos Servidores.

Hyper-V no se instala de forma predeterminada en los sistemas Windows, se debe instalarlo antes de poder usarlo. El equipo debe tener activo la compatibilidad de BIOS de Virtualización. 


.. figure:: ../images/install/07.png

.. figure:: ../images/install/08.png

.. figure:: ../images/install/09.png

.. figure:: ../images/install/10.png

.. figure:: ../images/install/11.png

.. figure:: ../images/install/12.png

.. figure:: ../images/install/13.png

.. figure:: ../images/install/14.png

.. figure:: ../images/install/15.png

.. figure:: ../images/install/16.png

.. figure:: ../images/install/17.png

.. figure:: ../images/install/18.png

.. figure:: ../images/install/19.png

.. figure:: ../images/install/20.png

.. figure:: ../images/install/21.png

Se debe reiniciar le servidor

Listo ya tenemos instalado el Hyper-V

.. figure:: ../images/install/22.png

.. figure:: ../images/install/23.png

