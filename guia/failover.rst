failover.rst


En el nodo01.dominio.local se debe ejecutar el comando te Trusted Host.
	winrm set winrm/config/client '@{TrustedHosts="nodo02.dominio.local"}'

En el nodo02.dominio.local se debe ejecutar el comando te Trusted Host.
	winrm set winrm/config/client '@{TrustedHosts="nodo01.dominio.local"}'

Habilitamos la replicación en el nodo01.dominio.local

.. figure:: ../images/failover/01.png

.. figure:: ../images/failover/02.png

.. figure:: ../images/failover/03.png

.. figure:: ../images/failover/04.png

.. figure:: ../images/failover/05.png

Habilitamos en le Firewall el puerto para la replicación, los hacemos de en el nodo01.dominio.local

.. figure:: ../images/config/66.png


En el nodo01.dominio.local se debe ejecutar el comando te Trusted Host.::

	winrm set winrm/config/client '@{TrustedHosts="nodo02.dominio.local"}'

.. figure:: ../images/failover/05.png

En el nodo02.dominio.local se debe ejecutar el comando te Trusted Host.::

	winrm set winrm/config/client '@{TrustedHosts="nodo01.dominio.local"}'

.. figure:: ../images/failover/07.png

Si no ejecutamos los comando anteriores tendremos el siguiente problema cuando desde la Consola de Hyper-V queramos ingresar a otros servidores.

.. figure:: ../images/failover/09.png

.. figure:: ../images/failover/08.png


Ahora vamos a planificar un Failover


.. figure:: ../images/failover/10.png

.. figure:: ../images/failover/11.png

.. figure:: ../images/failover/12.png

Debemos hacer Turn Off de la Maquina Virtual y lo intentamos nuevamente 

.. figure:: ../images/failover/13.png

.. figure:: ../images/failover/14.png

.. figure:: ../images/failover/15.png


.. figure:: ../images/failover/21.png

.. figure:: ../images/failover/16.png

Vemos como cambio ahora el Primario y el Replicador


.. figure:: ../images/failover/17.png

Nos vamos al nodo02.dominio.local y vemos el estado de la maquina virtual.

.. figure:: ../images/failover/18.png

Ahora para regresarlo al nodo01.dominio.local hacemos los mismos pasos de Planned Failover. Apagamos la maquina virtual


.. figure:: ../images/failover/19.png

.. figure:: ../images/failover/20.png

.. figure:: ../images/failover/21.png

.. figure:: ../images/failover/22.png


Nos vamos al nodo01.dominio.local y vemos que el estatus de la maquina virtual

.. figure:: ../images/failover/23.png


Listo...!!!
