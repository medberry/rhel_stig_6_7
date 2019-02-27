Cerner POC 2019-02-25
STIG Compliance and Remediation

As noted below, you ALWAYS want to run this playbook with tags. I need to put in an error condition if
tags is blank.
ANSIBLE_DEPRECATION_WARNINGS=false ANSIBLE_LOG_PATH=./ansible.log ansible-playbook -i ../centos.inventory    -u centos --check --diff -v  aex-oneoff.yml  --tags "AEX_001,check-mode-tag"  --skip-tags audit,prelim_tasks   -l centos6old
# This ^ is a oneline invocation of running the Altiris AEX
ANSIBLE_DEPRECATION_WARNINGS=false ANSIBLE_LOG_PATH=./ansible.log ansible-playbook -i ../centos.inventory    -u centos --check --diff  site.yml  --tags "check-mode-tag,V-38668,V-38617,V-38475,V-38649,RHEL-07-020230,RHEL-07-021710,RHEL-07-040110,RHEL-07-010280,RHEL-07-020240,V-38454"  --skip-tags audit,prelim_tasks   -l centos6:centos7
# This is a complete RHEL6 and RHEL7 audit/check-mode run
ANSIBLE_DEPRECATION_WARNINGS=false ANSIBLE_LOG_PATH=./ansible.log ansible-playbook -i ../centos.inventory    -u centos --check --diff  oneoff.yml  --tags "ONEOFF-001,check-mode-tag,V-38668,RHEL-07-010280"  --skip-tags audit,prelim_tasks   -l centos6:centos7
# This is the oneoff RPM validation test.
