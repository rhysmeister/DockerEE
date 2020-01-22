# DockerEE
A box to play around with Docker EE

# Setup

* Put your docker_subscription.txt file into the files/ dir. This is downloaded from your Docker Hub account.
* Put your Docker Enterprise download url into a vault encrypted file called vault.yml in the following format...

```
docker_ee_download_url: https://storebits.docker.com/ee/trial/sub-my-unique-id
```

Encrypt with...

```
ansible-vault encrypt vault.yml
```
