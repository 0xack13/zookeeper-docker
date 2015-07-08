# zookeeper-docker
Docker container for a development environment for Apache Zookeeper

Run the image:

```shell
docker run 0xack13/zookeeper:3.4.6
```

Here's a quick example to connect to Zookeeper using Python library "KazooClient":

```python

 from kazoo.client import KazooClient
 def my_listener(state):
  if state == KazooState.LOST:
   print "Lost!"
  elif state == KazooState.SUSPENDED:
   print "Suspended!"
  else:
   print "Neither.."
 #IP Address: boot2docker ip
 zk = KazooClient(hosts='172.17.0.24:2181')
 zk.start()
 zk.add_listener(my_listener)
 zk.stop()

```
