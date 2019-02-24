Cerner POC 2019-02-25
STIG Compliance and Remediation

As noted below, you ALWAYS want to run this playbook with tags. I need to put in an error condition if
tags is blank.

ansible-playbook  -u centos site.yml -lcentos6old --tags "V-38668,V-38587"
ansible-playbook  -u centos site.yml -l centos6 --tags "V-38668,V-38587,V-38481"
ansible-playbook  -u centos --check --diff -vvvv  site.yml -l centos6 --tags "V-38668,V-38587,V-38481"
ansible-playbook  -u centos --check --diff -vvvv  site.yml -l centos6 --tags "V-38668,V-38587,V-38481,V-38617,V-38475,V-38649"
ansible-playbook  -u centos --check --diff -v  site.yml -l centos6 --tags "V-38668,V-38587,V-38481,V-38617,V-38475,V-38649" --skip-tags audit
ansible-playbook   -u centos  --diff  site.yml -l centos6:centos7 --tags "V-38668,V-38587,V-38481,V-38617,V-38475,V-38649,RHEL-07-020230,RHEL-07-021710,RHEL-07-020260,RHEL-07-040110,RHEL-07-010280,RHEL-07-020240" -v --skip-tags audit,prelim_tasks
#checkjob
ansible-playbook   -u centos --check --diff  site.yml -l centos6:centos7 --tags "V-38668,V-38587,V-38481,V-38617,V-38475,V-38649,RHEL-07-020230,RHEL-07-021710,RHEL-07-020260,RHEL-07-040110,RHEL-07-010280,RHEL-07-020240" -v --skip-tags audit,prelim_tasks
sudo -v;ansible-playbook   -u centos --check --diff  site.yml  --tags "V-38668,V-38587,V-38481,V-38617,V-38475,V-38649,RHEL-07-020230,RHEL-07-021710,RHEL-07-020260,RHEL-07-040110,RHEL-07-010280,RHEL-07-020240,check-mode-tag"  --skip-tags audit,prelim_tasks   -l centos6old2:centos7new1
