DSM7 LITE (Actualizado hasta DSM 7.2)

AVISO: Cualquier error o daño en el dispositivo, es responsabilidad, exclusivamente de su propietario.

CONSEJO: Haga una copia de seguridad completa de su NAS, antes de este procedimiento.

Mediante este procedimiento, eliminaremos paquetes que se instalan por defecto en DSM7, y que no podemos desinstalar desde el entorno gráfico.
Con ello conseguiremos unos 200 Mb, de ahorro de memoria RAM, y que el NAS entre en hibernación y/o se apague, en una mayor cantidad de configuraciones.

Por supuesto, si se desea utilizar, alguno de los paquetes y servicios, nombrados a continuación, debe omitirse su desinstalación.

Una vez terminada la instalación de DSM7, saltará una pantalla que nos invita a activar, una serie de servicios de Synology, le decimos que no.

- Paquetes a desinstalar desde escritorio DSM
- DNS Server
- ActiveInsight

- Paquetes a desinstalar desde terminal:
  
  `1: Entramos por SSH al NAS.`
  
  `2: sudo -i`

  `synopkg uninstall SecureSignIn (PRECAUCIÓN: El 2fa depende de este paquete desde la 7.2)`

  `synopkg uninstall ScsiTarget (PRECAUCIÓN: Desinstalar, solo hasta la versión 7.1.1)`

Otros paquetes:

`synopkg uninstall HybridShare`

`synopkg uninstall Python2`

`synopkg uninstall SynoFinder`

`synopkg uninstall SMBService`

`synopkg uninstall SynoOnlinePack_v2`

`synopkg uninstall SupportService`

`synopkg uninstall QuickConnect`

- Desactivar aviso sobre el usuario admin
  
`3: sudo vi /usr/syno/synoman/webman/modules/DisableAdminNotification/config`

`Buscar "autoLaunch":true`

`Cambiar por "autoLaunch":false`

- Desactivar la comprobación de compatibilidad de las unidades de almacenamiento:
  
`4: cd /etc.defaults/`

`5: vi synoinfo.conf`

`Buscar support_disk_compatibility="yes"`

`Cambiar a “no”.`

Para comprobar los paquetes que tenéis instalados:

`synopkg list --name`

Para instalar un paquete:

`synopkg install_from_server nombrepaquete`

Actualizado: 27/07/2023
