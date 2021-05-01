# patch-for-BBR
Integration of Virtual machine scheduling conditions and BBR's model for cloud networks.

This patch is for BBRv1 https://git.kernel.org/pub/scm/linux/kernel/git/netdev/net-next.git/snapshot/net-next-4.20.tar.gz

To use patchedBBR, follow these steps:

  git clone git://git.kernel.org/pub/scm/linux/kernel/git/davem/net-next.git //clone Linux kernel
  
  git clone git@github.com:phuonghaunl/patchedBBR.git //clone patchedBBR
  
  cd net-next/ && git checkout v4.20 && cd .. //checkout v4.20
  
  cd patchedBBR/ && cp tcp.h net-next/include/linux/ //copy changes in tcp.h, tcp_bbr.c, tcp_output.c to net-next
  
  cp tcp_bbr.c tcp_output.c net-next/net/ipv4/ 
  
  sudo make && sudo make modules_install && sudo make //compile and install the kernel 
