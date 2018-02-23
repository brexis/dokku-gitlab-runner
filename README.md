# Installation

```
# Host
$ dokku apps:create gitlab-runner
$ cd /var/lib/dokku/data/storage
$ mkdir -p gitlab-runner
$ sudo chown -R dokku:dokku gitlab-runner
$ sudo chmod -R 777 gitlab-runner
$ sudo chmod -R 777 /var/run/docker.sock
$ sudo dokku storage:mount gitlab-runner /var/lib/dokku/data/storage/gitlab-runner:/etc/gitlab-runner
$ sudo dokku storage:mount gitlab-runner /var/run/docker.sock:/var/run/docker.sock
$ dokku proxy:ports-add gitlab-runner http:8080:5000

# Local
$ git add remote dokku@host_ip:gitlab-runner
$ git push origin dokku
```
