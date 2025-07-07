Zabbix BGP IPv4/IPv6 SNMP plantilla para Cisco Routers

Plantilla oficial desarrollada y testeada por CRIX (Costa Rica Internet Exchange) para ayudar al monitoreo de sesiones BGP en IPv4 & IPv6 utilizando routers Cisco con SNMPv2.

✨ Características

✅ Descubrimiento automático de peers BGP (IPv4 & IPv6)

✅ Monitorea el estado de sesión BGP, ASN remoto y prefijos aceptados

✅ Genera alertas si una sesión no está en estado Established

✅ Usa value mapping para mostrar estados BGP legibles

✅ Diseñado para Cisco IOS XR (probado en NCS-5501)

📁 Archivos incluidos

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

⚙️ Cómo funciona

El template utiliza SNMPv2 para consultar la tabla extendida cbgpPeer2Table de la MIB CISCO-BGP4-MIB.

La regla de descubrimiento identifica automáticamente todos los peers BGP IPv4 e IPv6 activos usando cbgpPeer2RemoteAddr.

Por cada peer descubierto, Zabbix genera tres elementos:

Estado de sesión (cbgpPeer2State)

ASN remoto (cbgpPeer2RemoteAs)

Prefijos aceptados (cbgpPeer2AcceptedPrefixes)

Si la sesión no está en estado Established (6), se dispara una alerta.

El estado de la sesión se muestra con nombres legibles usando el Value Mapping BGP Session State.

🚀 Ejemplo de monitoreo

Estado de sesión BGP (cbgpPeer2State)

ASN remoto del peer (cbgpPeer2RemoteAs)

Prefijos aceptados (cbgpPeer2AcceptedPrefixes)

🌐 Comunidad y autor

Desarrollado por: Carlos Pérez @C4rlosp

📝 Licencia

MIT. Puedes usar, modificar y compartir libremente este template.

