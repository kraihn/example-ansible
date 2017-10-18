# example-ansible

```yaml
stages:
  - test
  - deploy
 
test_syntax:
  stage: test
  script:
    - ansible-playbook -i hosts site.yml --syntax-check
 
test_dryrun:
  stage: test
  script:
    - ansible-playbook -i hosts site.yml --check
 
deploy:
  stage: deploy
  script:
    - ansible-playbook -i hosts site.yml
  only:
    - master
```
