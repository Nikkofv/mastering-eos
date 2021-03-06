.. _remote-access:

=========================
 Remote Access (SSH/VNC)
=========================

When not sitting at a physical machine in the EOS or Arch lab, EOS can be accessed from home using a protocol called Secure Shell (SSH). SSH gives you a prompt open to :ref:`bash`, the default shell on EOS. From this shell, you can run commands as you would inside a normal terminal emulator in an EOS desktop session. The commands will be run on the EOS machine to which you have connected.

SSH is a command-line-only technology. However, graphical remote access is available through a protocol called Virtual Network Computing (VNC). VNC allows access to a graphical desktop as if sitting at an EOS machine. Because the VNC protocol has no security of its own, our lab setup requires tunnelling VNC traffic through the SSH protocol. Each respective guide describes how to do this, but remember that you will first need to successfully set up SSH before attempting to use VNC.

The hostnames for the EOS machines are organized as follows: :samp:`eos{XX}.cis.gvsu.edu` where :samp:`{XX}` is 01 through 24 and :samp:`arch{XX}.cis.gvsu.edu` where :samp:`{XX}` is 01 through 10. Use these names to connect to a specific EOS machine.

Your SSH and VNC clients of choice depend on your machine's operating system.

.. toctree::
   :maxdepth: 2

   windows
   mac_os_x
   gnu_linux
