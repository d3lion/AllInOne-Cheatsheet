# Nmap (Network Mapper) 🎉

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/7/73/Logo_nmap.png" alt="Nmap Logo">
</p>

Nmap es una herramienta de escaneo de red libre y de código abierto utilizada para el descubrimiento de redes, auditoría de seguridad e inventario de redes. Se puede usar para descubrir hosts y servicios en una red informática, creando así un "mapa" de la red. Nmap es ampliamente utilizado por administradores de red, profesionales de seguridad y hackers. 🛠️

## Índice 📋

- [Básicos 🏗️](#básicos-️)
- [Escaneos Comunes 🌐](#escaneos-comunes-)
- [Detección de Sistema Operativo y Servicios 🖥️](#detección-de-sistema-operativo-y-servicios-️)
- [Escaneos de Puertos 🔍](#escaneos-de-puertos-)
- [Opciones de Salida 📝](#opciones-de-salida-)
- [Evadir Firewalls 🛡️](#evadir-firewalls-️)
- [Escaneos Avanzados 🧠](#escaneos-avanzados-)
- [Otras Utilidades ⚙️](#otras-utilidades-️)
- [Especificación de Objetivo 🎯](#especificación-de-objetivo-)
- [Descubrimiento de Hosts 🔍](#descubrimiento-de-hosts-)
- [Tiempo y Rendimiento ⏱️](#tiempo-y-rendimiento-️)
- [Tiempo y Rendimiento Switches ⏲️](#tiempo-y-rendimiento-switches-️)

## Características 🌟

- **Descubrimiento de Hosts**: Identifica dispositivos en una red. 🖥️
- **Escaneo de Puertos**: Enumera los puertos abiertos en los hosts objetivo. 📡
- **Detección de Servicios**: Determina qué servicios (incluyendo versiones) están ejecutándose en los puertos abiertos. 🔍
- **Detección del Sistema Operativo**: Detecta el sistema operativo y las características de hardware de los dispositivos de red. 🖱️
- **Interacción Scripting con el Objetivo**: Utiliza el Nmap Scripting Engine (NSE) para automatizar varias tareas de red. 📜
- **Salida Flexible**: Resultados de salida en varios formatos (texto plano, XML, etc.) para procesamiento adicional. 📄

## Instalación 🚀

### En Linux 🐧

```bash
sudo apt-get install nmap
```

### En macOS 🍏

```bash
brew install nmap
```

### En Windows 🪟

1. Descarga el instalador desde el [sitio web oficial de Nmap](https://nmap.org/download.html).
2. Ejecuta el instalador y sigue las instrucciones.

## Hoja de Trucos 📑

### Básicos 🏗️

```bash
nmap <target>            # Escaneo básico
nmap -sP <target>         # Descubrir hosts activos
nmap -sL <target>         # Lista de objetivos (sin escanear)
```

### Escaneos Comunes 🌐

```bash
nmap -sS <target>         # Escaneo SYN (rápido y sigiloso)
nmap -sT <target>         # Escaneo TCP connect
nmap -sU <target>         # Escaneo UDP
nmap -sN <target>         # Escaneo TCP Null
nmap -sX <target>         # Escaneo Xmas
nmap -sF <target>         # Escaneo FIN
nmap -sA <target>         # Escaneo TCP ACK
nmap -sW <target>         # Escaneo TCP Window
nmap -sM <target>         # Escaneo Maimon
```

### Detección de Sistema Operativo y Servicios 🖥️

```bash
nmap -O <target>          # Detectar sistema operativo
nmap -sV <target>         # Detectar versiones de servicios
nmap -A <target>          # Escaneo agresivo (OS, servicios, scripts)
nmap -sV 192.168.1.1 -sV  # Intentar determinar la versión del servicio en ejecución en el puerto
nmap -sV -version-intensity 192.168.1.1 -sV -version-intensity 8 # Nivel de intensidad de 0 a 9. Un número mayor aumenta la posibilidad de corrección.
nmap -sV -version-light 192.168.1.1 -sV -version-light # Habilitar modo ligero. Menor posibilidad de corrección. Más rápido.
nmap -sV -version-all 192.168.1.1 -sV -version-all # Habilitar nivel de intensidad 9. Mayor posibilidad de corrección. Más lento.
nmap -A 192.168.1.1 -A  # Habilita la detección del sistema operativo, la detección de versiones, el escaneo de scripts y el traceroute
nmap -O 192.168.1.1 -O  # Detección remota del sistema operativo usando la huella digital de la pila TCP/IP
nmap -O -osscan-limit 192.168.1.1 -O -osscan-limit # Si no se encuentra al menos un puerto TCP abierto y uno cerrado, no intentará la detección del sistema operativo contra el host
nmap -O -osscan-guess 192.168.1.1 -O -osscan-guess # Hace que Nmap adivine más agresivamente
nmap -O -max-os-tries 192.168.1.1 -O -max-os-tries 1 # Establecer el número máximo x de intentos de detección del sistema operativo contra un objetivo
nmap -A 192.168.1.1 -A  # Habilita la detección del sistema operativo, la detección de versiones, el escaneo de scripts y el traceroute
```

### Escaneos de Puertos 🔍

```bash
nmap -p 80 <target>       # Escanear un puerto específico
nmap -p 1-65535 <target>  # Escanear todos los puertos
nmap -p- <target>         # Escanear todos los puertos (forma abreviada)
nmap -p 21 <target>       # Escaneo de puerto específico
nmap -p 21-100 <target>   # Rango de puertos
nmap -p U:53,T:21-25,80 <target> # Escaneo de múltiples puertos TCP y UDP
nmap -p http,https <target> # Escaneo de puertos por nombre de servicio
nmap -F <target>          # Escaneo rápido de puertos (100 puertos)
nmap --top-ports 2000 <target> # Escanear los 2000 puertos más comunes
nmap -p-65535 <target>    # Escaneo desde el puerto 1 al 65535
nmap -p0- <target>        # Escaneo desde el puerto 0 al 65535
```

### Opciones de Salida 📝

```bash
nmap -oN output.txt <target>   # Salida normal
nmap -oX output.xml <target>   # Salida en XML
nmap -oG output.gnmap <target> # Salida en formato grepeable
nmap -oA output <target>       # Todas las salidas anteriores
nmap 192.168.1.1 -oN normal.file   # Salida normal al archivo normal.file
nmap 192.168.1.1 -oX xml.file      # Salida en XML al archivo xml.file
nmap 192.168.1.1 -oG grep.file     # Salida grepeable al archivo grep.file
nmap 192.168.1.1 -oA results       # Salida en los tres formatos principales a la vez
nmap 192.168.1.1 -oG -             # Salida grepeable a pantalla. También se puede usar -oN - y -oX -
nmap 192.168.1.1 -oN file.file -append-output    # Añadir un escaneo a un archivo de escaneo anterior
nmap 192.168.1.1 -v                # Aumentar el nivel de verbosidad (usar -vv o más para mayor efecto)
nmap 192.168.1.1 -d                # Aumentar el nivel de depuración (usar -dd o más para mayor efecto)
nmap 192.168.1.1 -reason           # Mostrar la razón por la cual un puerto está en un estado particular, misma salida que -vv
nmap 192.168.1.1 -open             # Mostrar solo puertos abiertos (o posiblemente abiertos)
nmap 192.168.1.1 -T4 -packet-trace # Mostrar todos los paquetes enviados y recibidos
nmap -iflist                       # Mostrar las interfaces del host y las rutas
nmap -resume results.file          # Reanudar un escaneo
```

### Evadir Firewalls 🛡️

```bash
nmap -f <target>          # Fragmentación de paquetes
nmap -D RND:10 <target>   # Señuelos para ofuscar origen
nmap -S <spoofed_ip> <target> # Suplantar IP de origen
nmap 192.168.1.1 -f       # El escaneo solicitado (incluidos los escaneos de ping) usa pequeños paquetes IP fragmentados. Más difícil para los filtros de paquetes
nmap 192.168.1.1 -mtu 32  # Establecer tu propio tamaño de desplazamiento
nmap -D 192.168.1.101,192.168.1.102,192.168.1.103,192.168.1.23 192.168.1.1 # Enviar escaneos desde IPs suplantadas
nmap -D decoy-ip1,decoy-ip2,your-own-ip,decoy-ip3,decoy-ip4 remote-host-ip # Ejemplo explicado anteriormente
nmap -S www.microsoft.com www.facebook.com # Escanear Facebook desde Microsoft (puede ser necesario -e eth0 -Pn)
nmap -g 53 192.168.1.1    # Usar el número de puerto de origen dado
nmap -proxies http://192.168.1.1:8080, http://192.168.1.2:8080 192.168.1.1 # Reenviar conexiones a través de proxies HTTP/SOCKS4
nmap -data-length 200 192.168.1.1 # Añadir datos aleatorios a los paquetes enviados
```

### Escaneos Avanzados 🧠

```bash
nmap --script vuln <target>    # Buscar vulnerabilidades conocidas
nmap --script http-* <target>  # Escanear scripts relacionados con HTTP
nmap -Pn <target>              # Saltar detección de host (tratar como activo)
nmap -sC 192.168.1.1 -sC       # Escanear con los scripts NSE predeterminados. Considerado útil para el descubrimiento y seguro
nmap 192.168.1.1 -script default          # Escanear con los scripts NSE predeterminados. Considerado útil para el descubrimiento y seguro
nmap 192.168.1.1 -script=banner           # Escanear con un solo script. Ejemplo: banner
nmap 192.168.1.1 -script=http*            # Escanear con un comodín. Ejemplo: http
nmap 192.168.1.1 -script=http,banner      # Escanear con dos scripts. Ejemplo: http y banner
nmap 192.168.1.1 -script "not intrusive"  # Escanear predeterminado, pero eliminar scripts intrusivos
nmap -script snmp-sysdescr -script-args snmpcommunity=admin 192.168.1.1  # Script NSE con argumentos
```

### Otras Utilidades ⚙️

```bash
nmap -sO <target>          # Escaneo de protocolos
nmap --top-ports 1000 <target> # Escanear los 1000 puertos más comunes
nmap --traceroute <target> # Realizar traceroute
nmap -Pn -script=http-sitemap-generator scanme.nmap.org  # Generador de mapa del sitio http
nmap -n -Pn -p 80 -open -sV -vvv -script banner,http-title -iR 1000  # Búsqueda rápida de servidores web aleatorios
nmap -Pn -script=dns-brute domain.com  # Fuerza bruta de nombres de host DNS adivinando subdominios
nmap -n -Pn -vv -O -sV -script smb-enum*,smb-ls,smb-mbenum,smb-os-discovery,smb-s*,smb-vuln*,smbv2* -vv 192.168.1.1  # Scripts SMB seguros para ejecutar
nmap -script whois* domain.com  # Consulta Whois
nmap -p80 -script http-unsafe-output-escaping scanme.nmap.org  # Detectar vulnerabilidades de cross-site scripting
nmap -p80 -script http-sql-injection scanme.nmap.org  # Verificar inyecciones SQL
```

### Especificación de Objetivo 🎯

```bash
nmap -p 22 <target>             # Escaneo específico del puerto 22
nmap -p 80,443 <target>         # Escaneo de puertos específicos múltiples
nmap -p 1000-2000 <target>      # Escaneo de rango de puertos

nmap 192.168.1.1/24            # Escaneo de una red completa en notación CIDR
nmap example.com               # Escaneo de un dominio
nmap 192.168.1.1-100            # Escaneo de un rango de IPs
nmap -iL targets.txt            # Leer objetivos desde un archivo
nmap -iR 100                    # Escaneo de 100 objetivos aleatorios
nmap <target> --exclude 192.168.1.1    # Excluir una IP específica
nmap <target> --exclude 192.168.1.1,192.168.1.2 # Excluir múltiples IPs
```

### Descubrimiento de Hosts 🔍

```bash
-sL	nmap 192.168.1.1-3 -sL	# No escanear. Solo listar objetivos
-sn	nmap 192.168.1.1/24 -sn	# Deshabilitar escaneo de puertos. Solo descubrimiento de hosts.
-Pn	nmap 192.168.1.1-5 -Pn	# Deshabilitar descubrimiento de hosts. Solo escaneo de puertos.
-PS	nmap 192.168.1.1-5 -PS22-25,80	# Descubrimiento TCP SYN en el puerto x. Puerto 80 por defecto.
-PA	nmap 192.168.1.1-5 -PA22-25,80	# Descubrimiento TCP ACK en el puerto x. Puerto 80 por defecto.
-PU	nmap 192.168.1.1-5 -PU53	# Descubrimiento UDP en el puerto x. Puerto 40125 por defecto.
-PR	nmap 192.168.1.1-1/24 -PR	# Descubrimiento ARP en red local.
-n	nmap 192.168.1.1 -n	# Nunca realizar resolución DNS.
```

### Tiempo y Rendimiento ⏱️

```bash
-T0	nmap 192.168.1.1 -T0	# Paranoid (0) para evasión de sistemas de detección de intrusos (IDS)
-T1	nmap 192.168.1.1 -T1	# Sneaky (1) para evasión de sistemas de detección de intrusos (IDS)
-T2	nmap 192.168.1.1 -T2	# Polite (2) ralentiza el escaneo para usar menos ancho de banda y recursos de la máquina objetivo
-T3	nmap 192.168.1.1 -T3	# Normal (3) que es la velocidad predeterminada
-T4	nmap 192.168.1.1 -T4	# Aggressive (4) acelera los escaneos; asume que estás en una red razonablemente rápida y confiable
-T5	nmap 192.168.1.1 -T5	# Insane (5) acelera el escaneo; asume que estás en una red extraordinariamente rápida
```

### Tiempo y Rendimiento Switches ⏲️

```bash
-host-timeout <time> nmap 192.168.1.1 -host-timeout 1s; 4m; 2h  # Abandonar el objetivo después de este tiempo
-min-rtt-timeout/max-rtt-timeout/initial-rtt-timeout <time> nmap 192.168.1.1 -min-rtt-timeout 1s; 4m; 2h  # Especifica el tiempo de ida y vuelta de la sonda
-min-hostgroup/max-hostgroup <size> nmap 192.168.1.1 -min-hostgroup 50; 1024  # Tamaños de grupos de escaneo de host en paralelo
-min-parallelism/max-parallelism <numprobes> nmap 192.168.1.1 -min-parallelism 10; 1  # Paralelización de sondas
-max-retries <tries> nmap 192.168.1.1 -max-retries 3  # Especificar el número máximo de retransmisiones de sondas de escaneo de puertos
-min-rate <number> nmap 192.168.1.1 -min-rate 100  # Enviar paquetes no más lento que <número> por segundo
-max-rate <number> nmap 192.168.1.1 -max-rate 100  # Enviar paquetes no más rápido que <número> por segundo
```

## Recursos Adicionales 📚

- [Documentación Oficial de Nmap](https://nmap.org/docs.html)
- [Guía de Uso de Nmap](https://nmap.org/book/man.html)
- [Repositorio en GitHub](https://github.com/nmap/nmap)

## Contribuciones 🤝

Las contribuciones son bienvenidas. Por favor, abre un issue o envía un pull request en el [repositorio de GitHub](https://github.com/nmap/nmap).

## Licencia 📜

Nmap se distribuye bajo la [Licencia GNU General Public License (GPL)](https://www.gnu.org/licenses/gpl-3.0.html).
```` ▋
