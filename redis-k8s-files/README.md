## Redis K8s Cluster Config

Create new namespace:

```
$ kubectl create ns redis
```

Command for install:

```
$ kubectl aplly -n redis -f .
```

Enter into the primary/master pod:

```
kubectl -n redis exec -it redis-0 -- sh
```

Connect to Redis using the Redis CLI:

```
redis-cli 
```

Authenticate yourself using the primary/master password, the password value is set in the configmap.yaml file on property authmaster:

```
auth admin
```

Create some key-value pair data using the following command:

```
set animal1 horse
set animal2 dog
```

Now get the key-value pair list:

```
keys *
```

Enter into the secondary/slave pod redis-1

```
Enter into the secondary/slave pod redis-1
```

Connect to Redis using the Redis CLI:
```
redis-cli 
```

Authenticate yourself using the secondary/slave password, the password value is set in the configmap.yaml file on property requirepass:

```
auth admin
```

Get the key-value pair list:

```
keys *
```