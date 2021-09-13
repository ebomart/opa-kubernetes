![img.shields.io](https://img.shields.io/badge/GITHUB-ACTION-blue?style=for-the-badge&logo=github)
![opa](https://img.shields.io/badge/OPA-K8S-orange?style=for-the-badge)
![shell-script](https://img.shields.io/badge/Shell_Script-121011?style=for-the-badge&logo=gnu-bash&logoColor=white)
# Open Policy Agent - Conftest

## What is conftest?

Conftest is a utility to help you write tests against structured configuration data. For instance you could write tests for your Kubernetes configurations, or Tekton pipeline definitions, Terraform code, Serverless configs or Docker configurations.

Conftest will test the data you provide it (Dockerfiles, Kubernetes manifests, etc) and compare it against rules written in the rego language used by `Open Policy Agent`.
By default Conftest will check the current working directory for a sub-directory named “policy”, rules in here will be evaluated against the data you’re testing.

## Usage in your repo:

Add the below code in your repo:


```yaml
    steps:
    - uses: actions/checkout@master
    - name: OPA Kubernetes
      uses: ebomart/opa-kubernetes@v1.0.0
      with:
        file: k8s_deployment.yaml
```

The Conftest Action has a small number of properties which map to the parameters for Conftest itself. These are passed to the action using with, as demonstrated with files in the above example.

| Property | Default   | Description  |   
|---        |---        |---|
| file      | -         | Kubernetes file to test  |
| output    | stdout    | How to format the output from Conftest  |
| policy   | policy    | Where to find the policy folder or files  |
