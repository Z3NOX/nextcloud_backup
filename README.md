# Backup files to your Nextcloud with Rclone and BorgBackup

Webspace like e.g. provided via Nextcloud can be used to backup files. A good backup stragegy should integrate as good as possible into your daily work, such that the backups can be done hassle-free. This description will show you how to use [BorgBackup](https://borgbackup.readthedocs.io/en/stable/index.html) to first create snapshots of your local data and later send them via [Rclone](https://rclone.org/) to your webspace. 

## BorgBackup
BorgBackup, or short simply "borg", is a python commandline tool, which lets you create archives of files with the following features:
 * **compression**: Files can be compressed
   with different methods if wanted
 * **deduplication**: If you happen to save
   one file multiple times into your archive,
   this data will be deduplicated and only be
   stored once from borg
 * **incremental backups**: If you from one backup
   to the next just change a tiny bit of your
   data, basically only this tiny bit gets
   saved. This opens the possiblity to do
   backups much quicker once you saved
   them for the first time. 
 * **encryption**: borg is able to encrypt the
   files stored in its backup archiv thus making
   it save to store them at an unsafe
   place - like "the Cloud".
   Because remember:
   
   ![There is no Cloud](images/nocloud.png)

## Rclone

To synchronise the archive made by borg to Nextcloud we use Rclone. Rclone is able to commuticate with a lot of storage providing software out there. So you might have a look at the [supported providers](https://rclone.org/#providers) if you are interested in using this documentation with something other than Nextcloud.

# Setting up BorgBackup to do its job
First you have to [install](https://borgbackup.readthedocs.io/en/latest/installation.html) borg. As it is available on the repositories of many platforms, it might just be as easy as
```
sudo apt install borgbackup
```
or
```
sudo pacman -S borg
```
