
# En el servidor
´´´bash
sudo apt-get install nfs-kernel-server portmap
sudo mkdir /mirror
sudo chown nobody:nogroup /mirror
ls -lta /mirror
´´´

### exportar NFS
´´´bash
sudo nano /etc/exports
´´´
agregar las lineas
> /mirror *(rw,sync)

´´´bash
sudo exportfs -a
sudo /etc/init.d/nfs-kernel-server start
cd /mirror
echo "william javier trigos guevara" >> contributors.txt
´´´


#en el cliente

### en la terminal
´´´bash
sudo mkdir -p /mirror
´´´

### agregar en**/etc/fstab**
´´´bash
sudo nano /etc/fstab
>192.168.100.100:/mirror /mirror nfs auto  0 0
sudo reboot
´´´

### verificar que podemos ver archivos del master
df -h
cd /mirror
ls -lta

