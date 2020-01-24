# DockerEE
A box to play around with Docker EE

# Setup

* Put your Docker Enterprise download url into a vault encrypted file called vault.yml in the following format...

```
docker_ee_download_url: https://storebits.docker.com/ee/trial/sub-my-unique-id
```

Encrypt with...

```
ansible-vault encrypt vault.yml
```

When Vagrant runs the Ansible Playbook you will be prompted for the vault password.

# Install UCP

```
docker container run --rm -it --name ucp \
   -v /var/run/docker.sock:/var/run/docker.sock \
   docker/ucp:2.2.5 install \
   --host-address <node-ip-address> \
   --interactive
```
