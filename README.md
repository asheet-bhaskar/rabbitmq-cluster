# rabbitmq-cluster

Steps to form rabbitmq cluster

1. Run following containers to spawn three independent rabbitmq containers
```
docker-compose up
```

2. Get the containers references using following command
```
docker ps
```

3. Exec into rabbitmq containers
```
docker exec -it {rabbitmq conatiner reference} bash
```

4. Check the status of cluster in each of the containers
```
rabbitmqctl cluster_status
```
each of the conatiner must have only itself one node in their cluster

5. Pick one of the containers, stop the rabbitmq app,  reset the state of the node and join the cluster of some other node
```
rabbitmqctl stop_app
rabbitmqctl reset
rabbitmqctl join_cluster rabbit_one@rabbit_one  //example
```

6. Check the status of cluster in each of the containers

7. Follow the step 5 for remaining container as well.
