
load('ext://helm_resource', 'helm_resource', 'helm_repo')
helm_repo('hashicorp', 'https://helm.releases.hashicorp.com')
helm_resource(name='vault', chart='hashicorp/vault', flags=['--values', 'vault-values.yaml'])
k8s_resource(workload='vault', port_forwards=(port_forward(local_port=8200, container_port=8200, name='Vault UI - token is "root"', link_path='ui',)))

k8s_yaml("nginx-deployment.yaml")