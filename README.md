

### paranoid hacker live system

**So far this is an extremly rough draft with zero peer review. So don't use it unless you intend to modify it and make it work properly.**



#### project objective:

This project's objective is to help people in oppressive surveillance states protect their security, confidentiality and anonymity.
This hardened bootable Debian-Live distro... ships with Tahoe-LAFS which can be used for backups and also as a tool
to assist in retaining the authenticity and confidentiality of your data whilest traveling. Operational security for border crossing
means wiping your drives (and or smashing with a hammer into tiny peices) AFTER you secure your Tahoe-LAFS backup and restore procedure.

**paranoid hacker preflight opsec checklist**

1. backup data to Tahoe-LAFS grid (sensitive documents, cryptographic key material etc.)
2. encrypt with passphrase the Tahoe-LAFS connecting information and root cryptographic capability; call it the ciphertext blob
3. send the ciphertext blob via another crypto messaging system to several friends (i prefer Pond)
4. wipe drives and or smash with hammer into tiny tiny bits

**note:** if you forget your passphrase then you are screwed, if they torture you and you tell them how to get the ciphertext blob and the passphrase to decrypt it then you lose.



#### design goals:

- "Tahoe-LAFS border crossing wizard" helps you keep your data safe so you can wipe (or physically destroy) your drives before crossing border and security checkpoints

- Debian live system configured especially to protect anonymity (Tor only iptables ruleset + macchanger)
'
- Mempo (deterministically built) grsecurity linux kernel

- encrypted persistent volume (luks + ext4)

- pre-installed with all the best crypto tools: *Tahoe-LAFS*, Pond, xmpp-client and gpg (not in the "best" category but still necessary).

- no user login prompt... only passphrase for crypto volume

- if sudo access is desired then the user can change their password (change will not survive reboot)

- dwm or xmonad only! (no shitty window managers like gnome or whatever the kids use thesedays)


#### suggestions welcome

* [https://github.com/david415](https://github.com/david415)

* [https://www.lumiere.net/~mrdavid/contact.txt](https://www.lumiere.net/~mrdavid/contact.txt)

