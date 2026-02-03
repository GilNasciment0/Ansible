# Repositorio Semaphore - Playbooks Ansible

Este repositorio contem playbooks Ansible para uso no Semaphore.

## Estrutura

- `playbooks/`: playbooks Ansible.
- `inventory_ips.yaml`: exemplo de inventario por IP.
- `inventory_hostnames.yaml`: exemplo de inventario por hostname.

## Playbooks

1. `playbooks/limpar_logs_docker.yml`
   - Trunca os arquivos de log JSON dos containers Docker em `/var/lib/docker/containers`.

2. `playbooks/verificar_zabbix_agent.yml`
   - Detecta `zabbix-agent` ou `zabbix-agent2`.
   - Verifica se o servico esta ativo e inicia se estiver inativo.

3. `playbooks/common.yaml`
   - Atualiza pacotes em Debian/Ubuntu e RedHat.
   - Instala pacotes basicos.
   - Cria usuario padrao (senha via `user_password`).

4. `playbooks/Install_docker.yaml`
   - Instala Docker Engine e plugins oficiais em Debian/Ubuntu.
   - Configura repositorio e keyring.
   - Adiciona usuario ao grupo `docker`.

5. `playbooks/criaruser.yaml`
   - Cria usuario com senha obrigatoria via `user_password`.
   - Ajusta grupo conforme familia (Debian/RedHat).

6. `playbooks/hardening_basico.yaml`
   - Hardening basico multi-distro.
   - Firewall habilitado para Debian/RedHat.
   - PF no FreeBSD desativado por padrao.

7. `playbooks/firewall_basico.yaml`
   - Firewall basico multi-distro.
   - UFW para Debian/Ubuntu.
   - Firewalld para RedHat/CentOS.
   - PF no FreeBSD desativado por padrao.

## Inventario

Os inventarios de exemplo estao na raiz do repositorio em formato YAML. No Semaphore, voce pode usar:

- `inventory_ips.yaml`
- `inventory_hostnames.yaml`

Ou continuar usando inventarios gerenciados diretamente na interface do Semaphore.

## Como usar no Semaphore

1. Crie/edite um template apontando para este repositorio.
2. Selecione o inventario desejado.
3. Escolha o playbook em `playbooks/`.

