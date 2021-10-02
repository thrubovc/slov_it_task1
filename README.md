# Slovensko IT assignment for DevOps - found [here](https://gitlab.com/devops301/hireme/-/tree/master/task1)

## Assumptions:
* `git` and `ansible` are installed
* the target machine is either Debian, Ubuntu, Centos or RHEL
* the user account used to run the playbook is root or has sudo rights with password authentication, so we use the `-K` switch
* the user account used to run the playbook can ssh to the target machine using a password, so we use the `-k` switch
* there might already be an http server running on port 80 on the target machine, so we use another port - `12380`
* the ansible playbook is executed on the target machine

## Instructions:
`ansible-galaxy collection install community.docker`<br>
`git clone https://github.com/thrubovc/slov_it_task1.git && cd slov_it_task1`<br>
`ansible-playbook -Kk playbook.yml`

Alternatively, the following variables are available: `containerName`, `imageName`, `tag`, `hostPort`. All of them are optional. You can specify one or multiple custom values by using the `-e` flag when running the playbook with each variable, example:

`ansible-playbook -kK -e hostPort=80 -e containerName=tomasko -e imageName=tomasko -e tag=1 playbook.yml`

You can also declare the values for these variables in code. For more info, see [Where to set variables](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html#where-to-set-variables)
