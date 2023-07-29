## CONTAINER_BUILDER
This project builds containers using Ansible. The containers are defined as hosts in the Ansible inventory. They are generated using host and group variables, templates and local connection.

### Containers build info
| Container Directory  | Container Image  | Version  |
|---|---|---|
| [ansible-docker-ci](ci/ansible-docker-ci/)| [quay.io/krestomatio/ansible-docker-ci](https://quay.io/krestomatio/ansible-docker-ci) | 0.4.15 |
| [ansible-operator-ci](ci/ansible-operator-ci/)| [quay.io/krestomatio/ansible-operator-ci](https://quay.io/krestomatio/ansible-operator-ci) | 0.4.15 |
| [ansible-podman-ci](ci/ansible-podman-ci/)| [quay.io/krestomatio/ansible-podman-ci](https://quay.io/krestomatio/ansible-podman-ci) | 0.4.15 |
| [ansible](ci/ansible/)| [quay.io/krestomatio/ansible](https://quay.io/krestomatio/ansible) | 0.4.15 |
| [centos:8-base](centos/centos8-base/)| [quay.io/krestomatio/centos:8-base](https://quay.io/krestomatio/centos) | 8.6.2 |
| [centos:8-minimal](centos/centos8-minimal/)| [quay.io/krestomatio/centos:8-minimal](https://quay.io/krestomatio/centos) | 8.6.2 |
| [centos:9-base](centos/centos9-base/)| [quay.io/krestomatio/centos:9-base](https://quay.io/krestomatio/centos) | 9.0.21 |
| [centos:9-minimal](centos/centos9-minimal/)| [quay.io/krestomatio/centos:9-minimal](https://quay.io/krestomatio/centos) | 9.0.21 |
| [go:1.18-toolset](go/go118-toolset/)| [quay.io/krestomatio/go:1.18-toolset](https://quay.io/krestomatio/go) | 1.18.17 |
| [httpd:2.4](httpd/httpd24/)| [quay.io/krestomatio/httpd:2.4](https://quay.io/krestomatio/httpd) | 2.4.17 |
| [keydb:6.3.3](keydb/keydb63/)| [quay.io/krestomatio/keydb:6.3.3](https://quay.io/krestomatio/keydb) | 6.3.3 |
| [moodle:4.1](moodle/moodle41/)| [quay.io/krestomatio/moodle:4.1](https://quay.io/krestomatio/moodle) | 4.1.4 |
| [moodle:4.1-bundle](moodle/moodle41_bundle/)| [quay.io/krestomatio/moodle:4.1-bundle](https://quay.io/krestomatio/moodle) | 4.1.4 |
| [moodle:4.1-httpd](moodle/moodle41_httpd24/)| [quay.io/krestomatio/moodle:4.1-httpd](https://quay.io/krestomatio/moodle) | 4.1.4 |
| [moodle:4.1-kio](moodle/moodle41_kio/)| [quay.io/krestomatio/moodle:4.1-kio](https://quay.io/krestomatio/moodle) | 4.1.4 |
| [moodle:4.1-nginx](moodle/moodle41_nginx120/)| [quay.io/krestomatio/moodle:4.1-nginx](https://quay.io/krestomatio/moodle) | 4.1.4 |
| [moodle:4.1-nginx_php-fpm](moodle/moodle41_nginx120_php80-fpm/)| [quay.io/krestomatio/moodle:4.1-nginx_php-fpm](https://quay.io/krestomatio/moodle) | 4.1.4 |
| [moodle:4.1-php-fpm](moodle/moodle41_php80-fpm/)| [quay.io/krestomatio/moodle:4.1-php-fpm](https://quay.io/krestomatio/moodle) | 4.1.4 |
| [nfs-ganesha:4.0.7](nfs-ganesha/nfs-ganesha40/)| [quay.io/krestomatio/nfs-ganesha:4.0.7](https://quay.io/krestomatio/nfs-ganesha) | 4.0.7 |
| [nginx:1.20](nginx/nginx120/)| [quay.io/krestomatio/nginx:1.20](https://quay.io/krestomatio/nginx) | 1.20.17 |
| [nginx:1.20-php-fpm](nginx/nginx120_php80-fpm/)| [quay.io/krestomatio/nginx:1.20-php-fpm](https://quay.io/krestomatio/nginx) | 1.20.17 |
| [node:14-ci](node/node14-ci/)| [quay.io/krestomatio/node:14-ci](https://quay.io/krestomatio/node) | 14.0.17 |
| [node:14](node/node14/)| [quay.io/krestomatio/node:14](https://quay.io/krestomatio/node) | 14.0.17 |
| [pgbouncer](pgbouncer/)| [quay.io/krestomatio/pgbouncer](https://quay.io/krestomatio/pgbouncer) | 0.4.15 |
| [php:8.0](php/php80-fpm/)| [quay.io/krestomatio/php:8.0](https://quay.io/krestomatio/php) | 8.0.17 |
| [postgres:13](postgres/postgres13/)| [quay.io/krestomatio/postgres:13](https://quay.io/krestomatio/postgres) | 13.0.17 |
| [rocky:8-base](rocky/rocky8-base/)| [quay.io/krestomatio/rocky:8-base](https://quay.io/krestomatio/rocky) | 8.8.2 |
| [rocky:8-minimal](rocky/rocky8-minimal/)| [quay.io/krestomatio/rocky:8-minimal](https://quay.io/krestomatio/rocky) | 8.8.2 |
| [rocky:9-base](rocky/rocky9-base/)| [quay.io/krestomatio/rocky:9-base](https://quay.io/krestomatio/rocky) | 9.2.2 |
| [rocky:9-minimal](rocky/rocky9-minimal/)| [quay.io/krestomatio/rocky:9-minimal](https://quay.io/krestomatio/rocky) | 9.2.2 |

### How to build them?
```bash
ansible-playbook .ansible-ci/build.yml
```

### Requirements
* Ansible >= 2.9
* docker or podman
* python docker
* [buildx](https://github.com/docker/buildx)
* see [requirements.txt](.ansible-ci/requirements.txt)

### Want to contribute?
* Context and dockerfile templates are inside each container's [directory](.ansible-ci/files/templated_contexts/). Some contexts and templates are reused by more than one container. Their respective variables generate different contexts in each container generated directory
* Variables can be changed inside [the inventory](.ansible-ci/inventory) dir
* Please modify or update only [templated context](.ansible-ci/files/templated_contexts/) or [the inventory](.ansible-ci/inventory)

### Directory layout
```
├── .ansible-ci             # ansible tasks to build and release container images
├── .lighthouse             # jenkins-x pipelines
└── */                      # directories where generated container contexts are saved
```
