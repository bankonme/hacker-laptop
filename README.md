

### paranoid hacker live system



#### project objective:

This project's objective is to help people in oppressive surveillance states protect their security, confidentiality and anonymity.
This minimal hardened bootable Debian-Live distro suggests using Tahoe-LAFS not only for frequent backups but as a tool
to assist in retaining the verifiability and confidentiality of your data whilest traveling.

**paranoid hacker preflight opsec checklist**

1. backup data to Tahoe-LAFS grid (sensitive documents, cryptographic key material etc.)
2. encrypt the Tahoe-LAFS connecting information and root cryptographic capability; call it the ciphertext blob
3. send the ciphertext blob via another crypto messaging system to several friends (i prefer Pond)
4. wipe drives and or smash with hammer into tiny tiny bits
5. smile at the airport security

**So far this is an extremly rough draft with zero peer review. So don't use it unless you intend to modify it and make it work properly.**



#### design goals:

- debian live system configured especially to protect anonymity (Tor only iptables ruleset + macchanger)

- mempo (deterministically built) grsecurity linux kernel

- optional encrypted persistent volume (luks + ext4)

- pre-installed with all the best crypto tools: *Tahoe-LAFS*, Pond, xmpp-client and gpg (not in the "best" category but still necessary).

- no user login prompt... only passphrase for crypto volume

- if sudo access is desired then the user can change their password (change will not survive reboot)

- dwm or xmonad only! (no shitty window managers like gnome or whatever the kids use thesedays)


#### suggestions welcome

* [https://github.com/david415](https://github.com/david415)

* [https://www.lumiere.net/~mrdavid/contact.txt](https://www.lumiere.net/~mrdavid/contact.txt)
