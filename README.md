# Repositorio Semaphore - Playbooks Ansible

Este repositorio contem playbooks Ansible para uso no Semaphore.

## Playbooks

1. `playbooks/limpar_logs_docker.yml`
   - Trunca os arquivos de log JSON dos containers Docker em `/var/lib/docker/containers`.

2. `playbooks/verificar_zabbix_agent.yml`
   - Detecta `zabbix-agent` ou `zabbix-agent2`.
   - Verifica se o servico esta ativo e inicia se estiver inativo.

## Inventario

O inventario e gerenciado diretamente no Semaphore (grupo `homologacao`).

## Como usar no Semaphore

1. Crie/edite um template apontando para este repositorio.
2. Selecione o inventario `homologacao`.
3. Escolha o playbook desejado.

