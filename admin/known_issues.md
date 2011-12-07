BISmark is in beta: what this means for you
===========================================

BISmark is still in "beta". This means that we are in the process of finding
and eliminating bugs that may affect the functionality or reliability of the
BISmark router or the BISmark measurement software. This document outlines
"known issues" (problems that we are aware of and working to fix), along with
tips to work around them, and the process to report other problems you
experience.

Known Issues
------------

### Sporadic wireless dropouts, mainly on 5 GHz radio ("BISmark5")

We have observed and received reports of intermittent wireless failures for
clients connected to the BISmark router. This appears to mainly affect clients
connected to the 5 GHz radio (wireless network named "BISmark5").  Clients
typically lose connectivity without disassociating from the wireless network,
and connectivity is later restored in approximately 10 minutes or less when the
client disassociates and reassociates with the network.

**Workarounds:**

- This problem seems to affect clients on the 2.4 GHz radio (wireless network
  named "BISmark") less frequently. Try connecting to this network instead.
- If you suddenly lose all connectivity to the Internet, disconnecting and
  reconnecting to the wireless network and/or turning wireless off and then on
  again will reestablish connectivity.
- If you have a machine that absolutely requires uninterrupted Internet
  connectivity, you should consider connecting it to the BISmark router with an
  ethernet cable.
- If this issues becomes extremely difficult to deal with, please contact
  <bismark-core@projectbismark.net> to discuss other options.

**Solutions:**

- We do not have a solution to this problem at this time, but a software update
  in the near future may improve wireless reliability and performance. We will
  notify you prior to deploying this update.

Reporting bugs and other problems
---------------------------------

If you experience any problems other than the problem described above, please
contact <bismark-core@projectbismark.net> to notify us and/or seek help.
