# Learn-Ansible

### The problem statement
I have a Roku TV on the boat that can take a USB storage device and play content without any network connection, but the media fies needs to be formated correctly.

Using *Handbreak CLI* I can convert the media using a Roku profile of **Roku 720p30 Surround** and with *mediainfo* I should be able to determine, if converstion is required.

I'll use rsync to keep the directory on my linux machine in sync with a USB 1TB NVME that runs stright from the TV due to it's low power consumption, this is a EXT3 filesytems.

The goal is to automate this using Ansible from my OSX laptop:


* use "vars.yaml" to define the list TV shows
* Mount my NAS using NFS (need to convert over NFS, as NAS does not support Handbreak and is underpowered)
* Convert anything that is not already setup for my Roku viewing (extra encoding is a waste of time and quaility)
* Mount my USB drive on the NAS
* Sync it to my USB drive
