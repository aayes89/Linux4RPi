# Linux4RPi
"Raspberry para Linux y Linux para todos"

# Descripción
Pruebe cualquier distribución de Linux (arm64 y armhf) en una Raspberry Pi 3. Actualmente probado con Debian (Stretch y Bullseye), Ubuntu, Kali-Linux Rolling y Void. Planeamos añadir soporte para ejecutar CD/DVD en modo Live para cada distribución.

# Componentes Necesarios
* Raspberry Pi 3 (se recomienda probar con la Pi 2 y versiones superiores)
* Tarjeta SD de al menos 2GB (o según el tamaño del CD/DVD)
* PC con lector CD/DVD (para realizar las instrucciones)
* Conexión a Internet (para descargar y actualizar repositorios, o tener un repositorio local)
* Editor de particiones: iMagicPro, gparted, PartitionMagic, PartitionGuru, etc.
* Paciencia (especialmente si desea configurar desde nivel base)
  
# Instrucciones
* Crear Particiones en la Tarjeta SD:
  - BOOT: Primera partición de 100MB en FAT16 (FAT32 también es compatible).
  - ROOT: Segunda partición en ext2, ext3 o ext4 (ocupará el espacio restante de la SD).
* Preparar la Partición BOOT:
  - Montar la partición BOOT.
  - Copiar y extraer el contenido del archivo comprimido (boot.zip) en la partición BOOT.
* Preparar la Partición ROOT:
  - Montar la partición ROOT.
  - Copiar el contenido desde la raíz del CD/DVD o de la imagen a ejecutar (bin, etc, usr, etc.).
* Finalizar y Ejecutar:
  - Desmontar la tarjeta SD del PC.
  - Conectar la tarjeta SD a la Raspberry Pi y encenderla.
  - Disfrutar de la distribución de Linux.
    
# Observaciones
* Proceso Simple pero Delicado:
  - Puede haber errores durante el arranque de la Raspberry Pi, especialmente si no está familiarizado con el procedimiento.
* Modificar Nombre de la Partición ROOT:
  - Si desea usar otro nombre para la partición ROOT, modifique el archivo cmdlines.txt en la instrucción root=...="ROOT".
* Uso de Imágenes Pre-elaboradas:
  - Para imágenes pre-elaboradas (squashfs o init-tranf), modifique el archivo cmdlines.txt en la instrucción root=ruta/imagen y añada su sistema de ficheros.
* Verificar Estado de Servicios:
  - Una vez ingresado al shell, ejecute journalctl -xe para ver el estado de cada servicio desde el arranque.
