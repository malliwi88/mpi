
# En el servidor
_ _ _


### Instalando los paquetes necesarios
```bash
sudo apt-get install nfs-kernel-server portmap
sudo mkdir /mirror
sudo chown nobody:nogroup /mirror
ls -lta /mirror
```

### exportar NFS
```bash
sudo nano /etc/exports
```
agregar las lineas al final del archico **`/etc/exports`**
> /mirror *(rw,sync)

```bash
sudo exportfs -a
sudo /etc/init.d/nfs-kernel-server start
cd /mirror
echo "william javier trigos guevara" >> contributors.txt
```


* * *

# En el cliente
_ _ _

### en una terminal
```bash
sudo mkdir -p /mirror
```
### Accediendo a NFS tras el booteo
```bash
sudo nano /etc/fstab
```

agregar al final del archivo **`/etc/fstab`**

>192.168.100.100:/mirror /mirror nfs auto  0 0

```bash
sudo reboot
```

### verificar que podemos ver archivos del master
```bash
df -h
cd /mirror
ls -lta
```

