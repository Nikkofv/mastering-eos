==========
 Mac OS X
==========

SSH
===

Mac OS X comes preinstalled with OpenSSH, the most popular implementation of the SSH protocol. The client can be run from the command-line and is simply called ``ssh``.

.. include:: common/openssh/connect.rst

.. include:: common/openssh/fingerprints.rst

.. include:: common/keys/intro.rst

.. code-block:: bash

    ssh smithj@eos01.cis.gvsu.edu 'umask u=rwx,go= && mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys' < ~/.ssh/id_rsa.pub

.. include:: common/keys/outro.rst

.. |text_editor| replace:: open -t
.. _mac-ssh-tunnel:
.. include:: common/openssh/forwarding.rst

The recommended VNC client for OS X is Chicken_, which is free and open-source software. Visit the website to download, install as you would any other Mac OS X application, and open.

You will be prompted to create a new server. If not prompted, click :menuselection:`Connection --> Open Connection...` from the menu bar. Double click "New Server" in the list on the left and rename it to "EOS", or create a new session with the :guilabel:`+` button if none exist. Leave the :guilabel:`Host` field as ``localhost`` or fill it in if missing. Leave the :guilabel:`Display or port` field at 0 or fill it in if missing.

Chicken has had some problems with the ZRLE encoding with our server. As this can cause a premature end to your session, our recommendation is to manually disable this encoding. To do this, first click the drop-down menu next to :guilabel:`Profile`, and click :guilabel:`Edit Connection Profiles...`. The :guilabel:`Profile Manager` configuration window will open. In the bottom left, enter "EOS" into the field and click the :guilabel:`+` button. Now click the checkbox next to the ZRLE encoding to disable it for EOS sessions. Close the :guilabel:`Profile Manager` window.

Click :guilabel:`Connect` to begin your VNC session with EOS. To connect in the future, select :menuselection:`Connection --> Open Connection...` from the menu, select your EOS configuration, and click :guilabel:`Connect`.

.. note:: Although Chicken offers an option to tunnel directly through SSH, we have not had luck using this option with our setup. We recommend sticking with the traditional SSH tunnel, as it is tested and works well.

.. _Chicken: http://sourceforge.net/projects/chicken/

Alternative Clients
===================

Chicken is not the only VNC viewer available for Mac OS X. Some alternatives are:

.. Note: We've considered using TigerVNC over Chicken as the primary client for Mac OS X. TigerVNC has no connection problems and is actively maintained. Chicken, on the other hand, has the issue with the ZRLE encoding and appears inactive. However, TigerVNC's interface is unintuitive, unattractive, and in general inferior to Chicken's. Given these tradeoffs, we've decided to stay with Chicken. If TigerVNC gets better or Chicken gets worse, we should consider switching to TigerVNC again.

* `TigerVNC <http://tigervnc.org/>`_ is a capable free and open source VNC viewer. Its interface is not as Mac-friendly as Chicken, but it works well. If you are having problems with Chicken, try TigerVNC.
* `RealVNC Viewer <http://realvnc.com/download/viewer/>`_ is a freeware viewer, but requires registration. RealVNC also offers `RealVNC Viewer for Google Chrome <https://chrome.google.com/webstore/detail/vnc-viewer-for-google-chr/iabmpiboiopbgfabjmgeedhcmjenhbla?hl=en>`_, a free Google Chrome extension which does not require registration.
* `JollysFastVNC <http://www.jinx.de/JollysFastVNC.html>`_ is a full-featured VNC client with trial and paid versions available.
* `Chicken of the VNC <http://sourceforge.net/projects/cotvnc/>`_ is an older version of Chicken and is not recommended.

.. include:: common/openssh/advanced/intro.rst

On Mac OS X, configuring your system to use our SOCKS proxy is quite simple. First, open :guilabel:`System Preferences`. From here, choose :menuselection:`Network --> Advanced... --> Proxies --> SOCKS Proxy`. Under the label :guilabel:`SOCKS Proxy Server`, enter ``localhost`` and ``5555`` to match the port passed to the ``-D`` flag. This can be any port as long as these numbers match. Check the box next to :guilabel:`SOCKS Proxy`, then click :guilabel:`OK` and :guilabel:`Apply` to turn on the proxy.

.. include:: common/openssh/advanced/outro.rst
