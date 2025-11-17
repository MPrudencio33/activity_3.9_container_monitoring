# activity_3.9_container_monitoring
Activity 3.9 Container Monitoring

Instructions:
Attach screenshot(s) of the following:
 • Your namespace
 • Show that your resources are deployed within your namespace /  Group Activity namespace (if it is a group activity)
 Submission would be your screenshots or Github repository (if you’ve pushed your manifest files

ANSWER:

1) Namespace (Group)

zanjero@ZANJERO:~/activity_3.9_container_monitoring$ kubectl get namespace
NAME                STATUS   AGE
cert-manager        Active   3h31m
default             Active   3h39m
external-dns        Active   3h31m
group-1-prom        Active   29m
group-4-prom        Active   41m
group-5-prom        Active   66m
group-99-prom       Active   7m31s
group-group2-prom   Active   20m
group2-prom         Active   33m
group3-prom         Active   102m
ingress-nginx       Active   3h32m
jiafu-prom          Active   4m25s
kube-node-lease     Active   3h39m
kube-public         Active   3h39m
kube-system         Active   3h39m
monitoring          Active   3h31m

2) Resources deployed within the group's namespace

zanjero@ZANJERO:~/activity_3.9_container_monitoring$ kubectl get all -n group-4-prom
NAME                                                       READY   STATUS    RESTARTS   AGE
pod/group-4-prom-prometheus-pushgateway-7969bdd86d-5ctnc   1/1     Running   0          44m
pod/group-4-prom-prometheus-server-8465df896-wvwjk         2/2     Running   0          44m

NAME                                          TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
service/group-4-prom-prometheus-pushgateway   ClusterIP   10.100.104.149   <none>        9091/TCP   44m
service/group-4-prom-prometheus-server        ClusterIP   10.100.28.35     <none>        80/TCP     44m

NAME                                                  READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/group-4-prom-prometheus-pushgateway   1/1     1            1           44m
deployment.apps/group-4-prom-prometheus-server        1/1     1            1           44m

NAME                                                             DESIRED   CURRENT   READY   AGE
replicaset.apps/group-4-prom-prometheus-pushgateway-7969bdd86d   1         1         1       44m
replicaset.apps/group-4-prom-prometheus-server-8465df896         1         1         1       44m