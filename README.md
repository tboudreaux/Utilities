# Utilities I have written for myself which I find helpful

## zfsSnapRestore
Utility for restoring files from zfs snapshots more easily

Note that you need vifm installed for this to work. Otherwise, it should
basically function. The utility will first use zpool list to find all zfs pools
and then for each pool it will attempt to located all datasets without
children. Each dataset without children will be listed as an avalible dataset
to restore from. 

Once you select the dataset you want to restore from teh utility will attempt
to fetch a list of all snapshots for that dataset (they must be in the
.zfs/snapshot directory for that dataset). Enter the number associated with the
dataset to restore from. Once in vifm select any files (not folders) you wish
to restore and then hit enter. The utility will tell you how many files were
selected and ask if you want to finish the restore. Once the the files are
restored they will be in their original location but with the file name changed
to include the snapshot label between the file name and extension. If the file
had no extension the snapshop label will become the extension. For example the
file test.mp4 on snapshot-daily-2020-04-02 will become
test.snapshot-daily-2020-04-02.mp4 and the file test will become
test.snapshot-daily-2020-04-02.

Hope this is helpful to others.
