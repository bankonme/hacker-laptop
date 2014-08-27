

### paranoid hacker live system


#### project objective:

This project's objective is to help people in oppressive surveillance states protect their security, confidentiality and anonymity.
So far this is an extremly rough draft with zero peer review.
Eventually after I enough of the problems I'd like to get my hacker friends to build it and try it out...


#### design goals:

- debian live system configured especially to protect anonymity (Tor only iptables ruleset + macchanger)

- mempo (deterministically built) grsecurity linux kernel

- pre-installed with all the best crypto tools: *Tahoe-LAFS*, Pond, xmpp-client and gpg (not in the "best" category but still necessary).

- no user login prompt... only passphrase for crypto volume

- if sudo access is desired then the user can change their password (change will not survive reboot)

- no shitty x-window managers: dwm or xmonad only!
(tiling window managers are clearly the best)


#### suggestions welcome (unless you hate tiling window managers):

[https://github.com/david415](https://github.com/david415)
[https://www.lumiere.net/~mrdavid/contact.txt](https://www.lumiere.net/~mrdavid/contact.txt)
