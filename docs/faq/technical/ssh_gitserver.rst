.. _ssh-gitserver:

============================================
How do I add a SSH key to my own git server?
============================================

Please add the SSH key to your authorized keys.

1. Save the provided SSH key as

::

    qc_rsa.pub

2. Run the following command in your terminal

::

    sudo cat qc_rsa.pub >> ~/.ssh/authorized_keys
