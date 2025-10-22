# TPnumero2AySO
33  sudo apt install lvm2
   34  sudo fdisk /dev/sdX
   35  200~sudo fdisk -l
   36  sudo fdisk -l
   37  sudo fdisk /dev/nvme0n1p2
   38  sudo fdisk -l
   39  sudo fdisk /dev/nvme0n1p1
   40  sudo fdisk /dev/sdb
   41  sudo fdisk /dev/nvme0n1p2
   42  sudo fdisk -l
   43  sudo dd if=/dev/zero of=/root/disco1.img bs=1M count=1024 
   44  sudo dd if=/dev/zero of=/root/disco2.img bs=1M count=2048 
   45  sudo dd if=/dev/zero of=/root/disco3.img bs=1M count=7168
   46  sudo losetup /dev/loop1 /root/disco1.img
   47  sudo losetup /dev/loop2 /root/disco2.img
   48  sudo losetup /dev/loop3 /root/disco3.img
   49  sudo losetup -a
   50  sudo pvcreate /dev/loop1
   51  sudo pvcreate /dev/loop2
   52  sudo pvcreate /dev/loop3
   53  sudo vgcreate nodocentral /dev/loop1
   54  sudo vgcreate nodocentral /dev/loop2
   55  sudo vgextend nodocentral /dev/loop2
   56  sudo vgextend nodocentral /dev/loop3
   57  sudo losetup -a
   58  sudo pvcreate /dev/loop1 /dev/loop2 /dev/loop3
   59  sudo vgremove nodocentral
   60  sudo lvremove /dev/nodocentral/*
   61  sudo pvremove /dev/loop1 /dev/loop2 /dev/loop3
   62  sudo wipefs -a /dev/loop1
   63  sudo wipefs -a /dev/loop2
   64  sudo wipefs -a /dev/loop3
   65  sudo pvcreate /dev/loop1 /dev/loop2 /dev/loop3
   66  sudo vgcreate nodocentral /dev/loop1 /dev/loop2 /dev/loop3
   67  sudo vgdisplay nodocentral
   68  sudo lvcreate -n sitios -L 3G nodocentral
   69  sudo lvcreate -n salvas -L 5G nodocentral
   70  sudo mkfs.ext4 /dev/nodocentral/sitios
   71  sudo mkfs.ext4 /dev/nodocentral/salvas
   72  sudo mkdir -p /mnt/sitios
   73  sudo mkdir -p /mnt/salvas
   74  sudo mount /dev/nodocentral/sitios /mnt/sitios
   75  sudo mount /dev/nodocentral/salvas /mnt/salvas
   76  df -h | grep nodocentral
   77  sudo lvs
   78  sudo lvextend -L 4G /dev/nodocentral/sitios
   79  sudo resize2fs /dev/nodocentral/sitios
   80  df -h | grep sitios
   81  sudo mkfs.ext4 /dev/nodocentral/sitios
   82  sudo mkfs.ext4 /dev/nodocentral/salvas
   83  sudo blkid | grep nodocentral
   84  sudo mkdir -p /mnt/sitios
   85  sudo mkdir -p /mnt/salvas
   86  sudo mount /dev/nodocentral/sitios /mnt/sitios
   87  sudo mount /dev/nodocentral/salvas /mnt/salvas
   88  df -h | grep nodocentral
   89  echo "Archivo de prueba" | sudo tee /mnt/sitios/prueba.txt
   90  cat /mnt/sitios/prueba.txt
   91  ls -l /mnt/sitios
   92  ls -l /mnt/salvas
   93  df -h /mnt/sitios /mnt/salvas
   94  sudo umount /mnt/sitios
   95  sudo umount /mnt/salvas
   96  df -h | grep sitios
   97  df -h | grep salvas
   98  sudo lvs
   99  sudo lvremove /dev/nodocentral/sitios
  100  sudo lvremove /dev/nodocentral/salvas
  101  sudo vgs
  102  sudo vgremove nodocentral
  103  sudo pvs
  104  sudo pvremove /dev/loop1 /dev/loop2 /dev/loop3
  105  sudo fdisk /dev/loop3
  106  sudo mkfs.ext4 /dev/loop3p1
  107  sudo mkfs.ext4 /dev/loop3p2
  108  sudo mkfs.ext4 /dev/loop3p3
  109  sudo mkfs.ext4 /dev/loop3p4
  110  sudo mkfs.ext4 /dev/loop3p5
  111  sudo mkfs.ext4 /dev/loop3p6
  112  sudo fdisk /dev/loop3
  113  sudo mkfs.ext4 /dev/loop3p1
  114  sudo mkfs.ext4 /dev/loop3p2
  115  sudo mkfs.ext4 /dev/loop3p3
  116  sudo mkfs.ext4 /dev/loop3p4
  117  sudo mkfs.ext4 /dev/loop3p5
  118  sudo mkfs.ext4 /dev/loop3p6
  119  sudo partprobe /dev/loop3
  120  lsblk /dev/loop3
  121  sudo mkfs.ext4 /dev/loop3p1
  122  sudo mkfs.ext4 /dev/loop3p2
  123  sudo mkfs.ext4 /dev/loop3p3
  124  sudo mkfs.ext4 /dev/loop3p4
  125  sudo mkfs.ext4 /dev/loop3p5
  126  sudo mkfs.ext4 /dev/loop3p6
  127  sudo mkdir -p /mnt/p{1,2,3,4,5,6}
  128  sudo mount /dev/loop3p1 /mnt/p1
  129  sudo mount /dev/loop3p2 /mnt/p2
  130  sudo mount /dev/loop3p3 /mnt/p3
  131  sudo mount /dev/loop3p4 /mnt/p4
  132  sudo mount /dev/loop3p5 /mnt/p5
  133  sudo mount /dev/loop3p6 /mnt/p6
  134  df -h | grep /mnt/p
  135  history > history.txt
facundo@facundo-Inspiron-3502:~$
