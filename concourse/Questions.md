
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
