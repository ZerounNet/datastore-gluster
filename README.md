# datastore-gluster

## chanage docker storege driver
  vim /etc/systemd/system/multi-user.target.wants/docker.service
  ExecStart=/usr/bin/dockerd -s btrfs

# restart dockerd
  systemctl restart docker.service

# mount dir
  mkdir /opt/datastore /opt/var/lib/glusterd -p

# start service
  docker service create --name datastore --mode global --mount type=bind,source=/opt/datastore,target=/opt/datastore --mount type=bind,source=/opt/var/lib/glusterd,target=/var/lib/glusterd --network swarm-network zerounnet/datastore-gluster
