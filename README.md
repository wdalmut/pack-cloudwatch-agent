# Install the agent

## Local configuration

You can tweak your configuration updating the `/etc/cloudwatch-agent/cloudwatch-agent.conf` file

A configuration example is:

```json
{
    "region": "eu-west-1",
    "address": "127.0.0.1",
    "port": 1234,
    "loop": 60
}
```

You can also configure AWS credentials using: `key` and `secret` but: put
your credentials into `/etc/default/cloudwatch-agent` is actually the preferrered configuration file

## RPM Packages

*Install RPM repo*

```
wget https://bintray.com/wdalmut/rpm/rpm -O bintray-wdalmut-rpm.repo
sudo mv bintray-wdalmut-rpm.repo /etc/yum.repos.d/
```

*Install the agent*

```
sudo yum install cloudwatch-agent.x86_64
```

*Configure your CloudWatch keys*

Edit file at: `/etc/default/cloudwatch-agent` and put your `KEY` and `SECRET`

*Run the service*

```
sudo service cw-agent start
```

You can check: `start`, `stop`, `restart`, `status`

## DEB Packages

*Install DEB repo*

```
echo "deb http://dl.bintray.com/wdalmut/deb /" | sudo tee /etc/apt/sources.list.d/wdalmut.list
echo "#deb-src http://dl.bintray.com/wdalmut/deb /" | sudo tee -a /etc/apt/sources.list.d/wdalmut.list
```

*Update your packages*

```
sudo apt-get update
```

*Install the agent*

```
sudo apt-get install cloudwatch-agent
```

*Configure your CloudWatch keys*

Edit file at: `/etc/default/cloudwatch-agent` and put your `KEY` and `SECRET`

*Run the service*

```
sudo service cw-agent start
```

You can check: `start`, `stop`, `restart`, `status`

