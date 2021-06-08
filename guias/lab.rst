Ejecutar estos comandos en el nodo01.dominio.local
	New-SelfSignedCertificate -DnsName “nodo01.dominio.local” -CertStoreLocation “cert:\LocalMachine\My” -TestRoot

	New-SelfSignedCertificate -DnsName “nodo02.dominio.local” -CertStoreLocation “cert:\LocalMachine\My” -TestRoot

En ambos servidores.
reg add “HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Virtualization\Replication” /v DisableCertRevocationCheck /d 1 /t REG_DWORD /f

En el nodo01.dominio.local se deben exportar los certificados y copiarlos en el nodo02.dominio.local:
	nodo02.dominio.local
	CertReq Test Root

En el nodo02.dominio.local se deben importar los certificados.
	nodo02.dominio.local dentro de certificados personales
	CertReq Test Root dentro de Trusted Root Certification Authorities

En el nodo01.dominio.local se deben importar el certificados.
	CertReq Test Root dentro de Trusted Root Certification Authorities

En el nodo01.dominio.local se debe ejecutar el comando te Trusted Host.
	winrm set winrm/config/client '@{TrustedHosts="nodo02.dominio.local"}'

En el nodo02.dominio.local se debe ejecutar el comando te Trusted Host.
	winrm set winrm/config/client '@{TrustedHosts="nodo01.dominio.local"}'

Crear una network
Crear una maquina virtual


.. figure:: ../images/keepalive.png
