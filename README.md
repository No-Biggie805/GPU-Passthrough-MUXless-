# GPU-Passthrough-MUXless-
My progress and annotations on my clevo notebook

Adding VFIO kernel params to GPU, SOURCE:https://wiki.archlinux.org/title/PCI_passthrough_via_OVMF

-sudo nano /etc/modprobe.d/vfio.conf
  options vfio-pci ids=10de:13d8

Load vfio early on mkinitcpio and ensure modconf is on hooks

-sudo nano /etc/mkinitcpio.conf
  MODULES=(... vfio_pci vfio vfio_iommu_type1 vfio_virqfd ...)
  HOOKS=(... modconf ...)

Update initramfs:
  sudo mkinitcpio -P

  Reboot
  
 Download ssd1.dat file, for fake battery: https://lantian.pub/usr/uploads/202007/ssdt1.dat  
                                           https://git.karaolidis.com/Nikas36/legion-7-vfio/-/blob/master/resources/SSDT1.dat
                                           

Now we edit xml after having windows 10 instaled.
