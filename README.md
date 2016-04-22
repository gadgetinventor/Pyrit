# pyrit
Automatically exported from code.google.com/p/pyrit

Pyrit allows to create massive databases, pre-computing part of the IEEE 802.11 WPA/WPA2-PSK authentication phase in a space-time-tradeoff. Exploiting the computational power of Many-Core- and other platforms through ATI-Stream, Nvidia CUDA and OpenCL, it is currently by far the most powerful attack against one of the world's most used security-protocols.

WPA/WPA2-PSK is a subset of IEEE 802.11 WPA/WPA2 that skips the complex task of key distribution and client authentication by assigning every participating party the same pre shared key. This master key is derived from a password which the administrating user has to pre-configure e.g. on his laptop and the Access Point. When the laptop creates a connection to the Access Point, a new session key is derived from the master key to encrypt and authenticate following traffic. The "shortcut" of using a single master key instead of per-user keys eases deployment of WPA/WPA2-protected networks for home- and small-office-use at the cost of making the protocol vulnerable to brute-force-attacks against it's key negotiation phase; it allows to ultimately reveal the password that protects the network. This vulnerability has to be considered exceptionally disastrous as the protocol allows much of the key derivation to be pre-computed, making simple brute-force-attacks even more alluring to the attacker. For more background see this article on the project's blog.

The author does not encourage or support using Pyrit for the infringement of peoples' communication-privacy. The exploration and realization of the technology discussed here motivate as a purpose of their own; this is documented by the open development, strictly sourcecode-based distribution and 'copyleft'-licensing.

Pyrit is free software - free as in freedom. Everyone can inspect, copy or modify it and share derived work under the GNU General Public License v3+. It compiles and executes on a wide variety of platforms including FreeBSD, MacOS X and Linux as operation-system and x86-, alpha-, arm-, hppa-, mips-, powerpc-, s390 and sparc-processors.

Attacking WPA/WPA2 by brute-force boils down to to computing Pairwise Master Keys as fast as possible. Every Pairwise Master Key is 'worth' exactly one megabyte of data getting pushed through PBKDF2-HMAC-SHA1. In turn, computing 10.000 PMKs per second is equivalent to hashing 9,8 gigabyte of data with SHA1 in one second. The following graph shows various performance numbers measured on platforms supported by Pyrit.

The following graph shows an example of multiple computational nodes accessing a single storage server over various ways provided by Pyrit:

* A single storage (e.g. a MySQL-server)
* A local network that can access the storage-server directly and provide four computational nodes on various levels with only one node actually accessing the storage server itself.
* Another, untrusted network can access the storage through Pyrit's RPC-interface and provides three computional nodes, two of which actually access the RPC-interface.

What's new

See http://pyrit.wordpress.com
How to use

Pyrit compiles and runs fine on Linux, MacOS X and BSD. I don't care about Windows; drop me a line (read: patch) if you make Pyrit work without copying half of GNU ...

A guide for installing Pyrit on your system can be found in the wiki. There is also a Tutorial and a reference manual for the commandline-client.
How to participate

You may want to read this wiki-entry if interested in porting Pyrit to new hardware-platform. Contributions or bug reports should be posted on the Issue-tracker. General questions get answered on Pyrit's mailing-list; just send an eMail to pyrit@googlegroups.com or see http://groups.google.com/group/pyrit.
