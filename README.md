# Ansible-GlusterFS Role

This role will mount a raw partition and create GlusterFS volumes within
a cluster and mount data with GlusterFS.

## Example

```yaml
---

xfs_disk: sdc
xfs_partition: /dev/sdc

xfs_mounts:
  - { path: /mnt/bricks/foo, name: foo }

glusterfs_mounts:
  - { path: /srv/data/foo, volume: foo, log: /var/log/gluster-foo.log }

glusterfs_cluster:
  - 192.168.0.1
  - 192.168.0.2
  - 192.168.0.3

# Ubuntu / Debian only
glusterfs_ppa_use: yes
glusterfs_ppa_version: 3.12
```
