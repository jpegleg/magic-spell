# magic-spell

A backup script that backs up most of remote server, minus some un-wanted directories, and encrypts it for storage with the public key of your choice using pgp (gpg).

Because of the way rsync works, it must be run as root to preserve the ownership and permissions of the files correctly.
