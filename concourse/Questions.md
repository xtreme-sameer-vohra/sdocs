
#Questions & Answers
- is missing since for vols that are in the db and not on the worker? does it work for volumes on the worker but not in the db ?

	if missing since flag is set, then volumes get deleted from the DB when the state is in VolumeCreated or VolumeFailed after 5 min grace interval

	the missing flag is set on `report volumes` API call to web, when a volume is in DB but not present in `report volumes` payload sent by the worker via TSA

- What causes missing_since flag to be set on a volume ? does it have to be stalled for that to happen ?
	not affected by worker status. It is set on `report volumes` call, see above for details.

- find the pre-stop step for when kubectl kill pod is called on concourse worker

- lockFactory works off DB ?

- does lockFactory ensure only 1 web node runs GC for each componentName ( volume ) at a time ?

- are we using PVCs for the workers ? so if a pod was re-created should it have lost the volumes at all ?
	init scripts clean this up

- What is the status quo for cow cow in Concourse ?
	* cow-cow vol uses cow-merged or cow-upper as cow-cow lower ?

- What is the difference between bind mount & overlay mount
	* both allow creation of a file system at a path and provide it to applications at another path - can use it to make "another path" appear to be writeable even though it may not be at the underlying level ( before the overlay or bind mount was applied eg. /var on a ro-roofts)

	* overlay is a VFS ( virtual file system implementation), bind mounts are implemented by VFS namespace facility
	
	* Reference - https://opensource.com/article/19/3/virtual-filesystems-linux
