# khw-notes

Personal notes for https://github.com/kelseyhightower/kubernetes-the-hard-way

Mainly snippets running the machines on mac using https://multipass.run

```shell
multipass launch jammy --name jumpbox --cpus 1 --memory 512MB --disk 10GB
multipass launch jammy --name node-1  --cpus 1 --memory 2GB   --disk 20GB
multipass launch jammy --name node-0  --cpus 1 --memory 2GB   --disk 20GB
multipass launch jammy --name server  --cpus 1 --memory 2GB   --disk 20GB
```

In addition to enabling root login,
this config file that disabled password auth has to be deleted:

```shell
rm -f /etc/ssh/sshd_config.d/60-cloudimg-settings.conf
systemctl restart sshd
```
