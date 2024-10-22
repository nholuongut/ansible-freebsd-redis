# freebsd_redis

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>


## Requirements

### Collections

- community.general


## Variables

See defaults and examples in vars.


## Workflow

1) Change shell to /bin/sh

```
shell> ansible dbserver -e 'ansible_shell_type=csh ansible_shell_executable=/bin/csh' -a 'sudo pw usermod freebsd -s /bin/sh'
```

2) Install the role and collections

```
shell> ansible-galaxy role install nholuong.freebsd_redis
shell> ansible-galaxy collection install community.general
```

3) Fit variables, e.g. in vars/main.yml

```
shell> editor nholuong.freebsd_redis/vars/main.yml
```

4) Create playbook and inventory

```
shell> cat redis.yml

- hosts: dbserver
  roles:
    - nholuong.freebsd_redis
```

```
shell> cat hosts
[dbserver]
<SERVER1-IP-OR-FQDN>
<SERVER2-IP-OR-FQDN>
[dbserver:vars]
ansible_connection=ssh
ansible_user=freebsd
ansible_python_interpreter=/usr/local/bin/python3.7
ansible_perl_interpreter=/usr/local/bin/perl
```

5) Install Redis

```
shell> ansible-playbook redis.yml -t bsd_redis_packages
```
		
6) Check the playbook

```
shell> ansible-playbook redis.yml --syntax-check
shell> ansible-playbook redis.yml --check --diff
```

7) Configure Redis

```
shell> ansible-playbook redis.yml
```


## References

- [Redis Quick Start](https://redis.io/topics/quickstart/)
- [Redis Configuration](https://redis.io/topics/config/)
- [Redis](https://redis.io/)
- [RedisLabs](https://redislabs.com/)


# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟