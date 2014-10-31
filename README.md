

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

- pre-installed with all the best crypto tools: *Tahoe-LAFS*, Pond, xmpp-client and gpg (necessary for Pond introductions).

- no user login prompt... only passphrase for crypto volume

- if sudo access is desired then the user can change their password (change will not survive reboot)

- dwm or xmonad only! (no shitty window managers like gnome or whatever the kids use thesedays)


#### usage:

This is my rough draft debian-live 3.x configuration.
You should read the debian-live 3.x documentation to understand how it works and how to use it.
It's pretty easy to use and customize to suite your needs.

http://live.debian.net/manual/3.x/html/live-manual.en.html

The build results in a `binary.hybrid.iso` file. Here's how I make a USB disk with an encrypted LUKS Persistent volume:


##### write hybrid iso image to a USB disk

If for instance the USB disk is /dev/sdc:
```bash
dd if=binary.hybrid.iso of=/dev/sdc bs=1M
```

##### create another partition on the USB disk

Then used gparted to create another partition with the label "persistence"...
just like the debian-live 3.x documentation says to do. =-)

```bash
sudo gparted /dev/sdc
```


##### create the LUKS volume

I think it's important to pay attention to the latest cipher format, encryption algorithms and key stretching:

```bash
cryptsetup --iter-time 10 --cipher aes-xts-plain64 --key-size 512 --hash sha512 luksFormat /dev/sdc
```


##### create the filesystem

Just like the debian-live 3.x documentation states, you must label
the filesystem with "persistence" :

```bash
# XXX prompts for passphrase, obviously
cryptsetup luksOpen /dev/sdc myLuks

mkfs -t ext4 -L persistence /dev/mapper/myLuks
```


##### place a persistence.conf onto the new filesystem

```bash
mount /dev/mapper/myLuks /mnt
# XXX choose your own adventure
cat <<EOT>/mnt/persistence.conf
/home
EOT
umount /mnt
cryptsetup luksClose myLuks
```


#### suggestions welcome

* [https://github.com/david415](https://github.com/david415)

* [https://www.lumiere.net/~mrdavid/contact.txt](https://www.lumiere.net/~mrdavid/contact.txt)

