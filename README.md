# Linux4RPi
"Raspberry para Linux y Linux para todos"
# Descripción 
Pruebe cualquier distro Linux (arm64 y armhf) en una Raspberry Pi 3. Comprobado actualmente por falta de tiempo, con Debian (Stretch y Bullseye), Ubuntu, Kali-Linux Rolling y Void.
<p>Queda pendiente utilizar CD/DVD en modo Live de cada una</p>

# Componentes
- Raspberry Pi 3 (habrá que probar con la 2 y superiores)
- SD card mínima de 2GB o según el tamaño del CD/DVD.
- PC con lector CD/DVD y/o ara realizar las instrucciones 
- Conexión a Internet (para descargar y actualizar repositorios, en caso contrario tener uno local)
- Editor de particiones: iMagicPro, gparted, PartitionMagic, PartitionGuru, etc. (importante, cualquier de ellos)
- Algo de paciencia (si quieres ir a nivel base)
  
# Instrucciones 
- Crear 2 particiones en la memoria SD (BOOT y ROOT)
La primera participación de 100MB en FAT16 (aunque FAT32 también funciona)
La segunda participación en ext2, ext3 o ext4. (mientras sea Linux no importa, pero que ocupe el espacio restante de la SD)
- Montar la partición BOOT
- Copiar y extraer el contenido del comprimido (boot.zip) en la partición
- Montar la partición ROOT
- Copiar el contenido desde la raíz del CD/DVD o la imagen a ejecutar (bin, etc, usr,...,)
- Desmontar memoria SD del PC
- Conectar a la Raspberry y disfrutar
  
# Observaciones 
Es un proceso relativamente simple pero sujeto a fallos. Durante el arranque de la Raspberry puede que se agobie con tanta información si no está acostumbrado. 

Si quiere usar otro nombre para la partición ROOT, debe modificar el archivo cmdlines.txt en la instrucción root=...="ROOT"

Si tiene una imagen pre-elaborada (squashfs o init-tranf), debe modificar el archivo cmdlines.txt en la instrucción root=ruta/imagen y añadir su sistema de ficheros.

Sugiero una vez ingrese al shell, ejecute <code>journalctl -xe</code> para poder ver cada servicio y su estado desde el arranque. 

