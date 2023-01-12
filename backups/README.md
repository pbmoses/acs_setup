This is a simple example of running ACS/Stackrox backups in a container and storing them on a persistent volume.

cron-backups.yaml creates a container from the roxctl image and runs a backup storing it in a PVC mounted on /mnt

You can utilize ROX_API_TOKEN as an env variable and store an API token in a secret
You can utilize ROX_CENTRAL_ADDRESS as an env variable as well
The above env variables were not used in this case with hopes of showing simple examples that could be built upon.
retreive-backups-pod.yaml creates a simple container that mounts a PVC where you could retrieve a backup, if needed. (obviously you need to mount the correct PVC)

There are many ways to achieve the backup task. This was done for an environment where access was limited and the ACS team only had access to persistent storage via the cluster.
