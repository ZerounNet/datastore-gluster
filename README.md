# datastore-gluster

# 
docker service create --name datastore --mode global --mount type=bind,source=/opt/datastore,target=/opt/datastore --network swarm-network zerounnet/datastore-gluster
