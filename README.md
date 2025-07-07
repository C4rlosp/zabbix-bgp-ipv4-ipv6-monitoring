Zabbix BGP IPv4/IPv6 SNMP Template for Cisco Routers (CRIX)

Official Zabbix template developed and tested by CRIX (Costa Rica Internet Exchange) for monitoring BGP IPv4 and IPv6 sessions on Cisco routers using SNMPv2.

✨ Features

✅ Auto-discovery of BGP peers (IPv4 & IPv6)

✅ Monitors BGP session state, remote ASN, and accepted prefixes

✅ Triggers alerts if a session is not in Established state

✅ Uses value mapping for clear BGP state names

✅ Designed for Cisco IOS XR (tested on NCS-5501)

📁 Files included

zabbix-bgp-ipv4-ipv6-template-crix/
├── templates/
│   └── zbx_template_bgp_ipv4_ipv6_crix_autodiscovery.yaml
├── screenshots/
│   ├── latest-data-example.png
│   └── telegram-alert-example.png
└── docs/
    └── how-it-works.md

⚙️ Requisitos

Zabbix 6.0 o 7.0

SNMPv2 habilitado en el router Cisco

Comunidad SNMP accesible desde el servidor Zabbix

MIB CISCO-BGP4-MIB activa

🔄 Instalación

Ir a Data Collection → Templates y crear manualmente un nuevo template llamado Template SNMP BGP IPv4-IPv6 Auto-Discovery.

Dentro del template, crear primero el value mapping llamado BGP Session State con los siguientes valores:

Valor

Estado

1

Idle

2

Connect

3

OpenSent

4

OpenConfirm

5

Active

6

Established

Luego, importar el archivo YAML: Configuration → Templates → Import

Zabbix solicitará reemplazar el template existente (mismo nombre). Hacer clic en Sí para que mantenga el value mapping y actualice el template.

Asignar el template al host Cisco con SNMPv2 habilitado

Asegurar que la comunidad SNMP y la ACL permiten el acceso

Esperar la ejecución del discovery (cada 5 min por defecto)

🚀 Ejemplo de monitoreo

Estado de sesión BGP (cbgpPeer2State)

ASN remoto del peer (cbgpPeer2RemoteAs)

Prefijos aceptados (cbgpPeer2AcceptedPrefixes)

🌐 Comunidad y autor

Desarrollado por el equipo técnico del CRIX – https://crix.crContact: Carlos Pérez @C4rlosp

📝 Licencia

MIT. Puedes usar, modificar y compartir libremente este template.
