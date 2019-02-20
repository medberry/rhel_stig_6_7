Cerner POC 2019-02-25
STIG Compliance and Remediation

ansible-playbook  -u centos site.yml -lcentos6old --tags "V-38668,V-38587"
ansible-playbook  -u centos site.yml -l centos6 --tags "V-38668,V-38587,V-38481"
ansible-playbook  -u centos --check --diff -vvvv  site.yml -l centos6 --tags "V-38668,V-38587,V-38481"
ansible-playbook  -u centos --check --diff -vvvv  site.yml -l centos6 --tags "V-38668,V-38587,V-38481,V-38617,V-38475,V-38649"
ansible-playbook  -u centos --check --diff -v  site.yml -l centos6 --tags "V-38668,V-38587,V-38481,V-38617,V-38475,V-38649" --skip-tags audit
