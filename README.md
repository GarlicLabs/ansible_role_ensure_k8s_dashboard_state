# ansible_role_ensure_k8s_dashboard_state

[![Validate infrastructure as code](https://github.com/garliclabs/ansible_role_ensure_k8s_dashboard_state/actions/workflows/validation.yml/badge.svg)](https://github.com/garliclabs/ansible_role_ensure_k8s_dashboard_state/actions/workflows/validation.yml)

Manages the deployment state and configuration of k8s dashboard via helm in a kubernetes cluster

## Requirements

Kubernetes, Helm, kubectl

## Role Variables

TODO

## Development

**k8s_dashboard_kubeconfig:** Path to the kubeconfig for your kubernetes cluster  
**#k8s_dashboard_value_path:** Set path to your own helm values file  
**k8s_dashboard_chart_version:** Version of kubernetes dashboard helm chart see: [Artifact hub](https://artifacthub.io/packages/helm/k8s-dashboard/kubernetes-dashboard)  
**k8s_dashboard_namespace:** Kubernetes namespace to deploy k8s dashboard in  
**k8s_dashboard_host_name:** URL where you want to reach the dashboard  
**k8s_dashboard_state:** State of the deployment, can be either present or absent  
**k8s_dashboard_banner:** Text that will be shown as banner inside the k8s dashboard  

### Testing

* Create venv: `python3 -m venv ./venv`
* Install pip requirements: `venv/bin/pip install -r pip_requirements.txt`
* Execute tests `venv/bin/molecule test`

### Linting & static security analyser

Both the linter and the static security analyser are running on each push on the github actions pipeline.  

* As linter [ansible-lint](https://ansible.readthedocs.io/projects/lint/) is used. For installation documentation see [ansible lint installing](https://ansible.readthedocs.io/projects/lint/)
  * Just run `ansible-lint`

* To check if there are any passwords, tokens... hardcoded, [kics](https://kics.io/index.html) is used to ensure a secure IaC repository.  
  * Run it locally `docker run -t -v $PWD:/path checkmarx/kics:latest scan -p /path -o "/path/"`

## Dependencies

* The server this role is executed need to have kubectl with a connection to the kubernetes you want to configure

## License

GNU General Public License version 3
