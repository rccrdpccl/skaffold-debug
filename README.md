1. gpg --import pgp/sops_functional_tests_key.asc
2. skaffold render | grep -A1 PASSWORD

Expected:
```yaml
- name: PASSWORD
  value: mysecretpassword
```

Actual:
```yaml
- name: PASSWORD
  value: ENC[AES256_GCM,data:BAyN6ZdiPG/c/roDuNr89w==,iv:kqj/6F+T1yozfFIu7Y6gMCFv08Fy19aBtU4nraF+JEQ=,tag:VF1p4Eq4DuR1FSLL/J0TNw==,type:str]
```
