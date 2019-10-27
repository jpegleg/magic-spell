# magic-spell

A backup script that backs up most of remote server (minus some un-wanted directories, special devices, src scraps, and log data), and encrypts it for storage with the public key of your choice using pgp (gpg).

Because of the way rsync works, it must be run as root to preserve the ownership and permissions of the files correctly.

Example usage:

chmod +x magic-spell
mv magic-spell /usr/local/sbin/
cp -r ~/.ssh /var/workspace/
magic-spell keeganbowen.com D9348300F93B589BFCB61242870C8F5DFE58219A /var/workspace/




Different style example usage as crontab, and with email public key identifier:

cp magic-spell /root/
chmod +x /root/magic-spell
mkdir /mnt/sas/.ssh
cp /home/adminuser/.ssh/id_rsa /mnt/sas/.ssh/
crontab -e

5 5 5 * * /root/magic-spell keeganbowen.com mykey@keeganbowen.com /mnt/sas/
