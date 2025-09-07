# Portfólio: Estudos e Projeto Final de Kubernetes

## 📖 Sobre o Projeto

Este repositório documenta minha jornada de aprendizado e aplicação prática dos conceitos de Kubernetes, realizados durante o curso da **Trilha DevOps Avançado** da **Ada Tech**. O programa faz parte do projeto **Data4All**, uma iniciativa com o valioso apoio da **Gerdau**.

Todo o conteúdo foi ministrado pelo instrutor **Wilton Guilherme**, a quem agradeço pelo excelente compartilhamento de conhecimento.

## 📂 Estrutura do Repositório

-   **/laboratorios**: Contém todos os manifestos `.yaml` desenvolvidos durante as aulas, cobrindo os conceitos fundamentais do Kubernetes.
-   **/projeto-final-voting-app**: Contém uma aplicação completa de microsserviços implantada no Kubernetes, servindo como projeto final para consolidar o aprendizado.

## 🚀 Projeto Final: Aplicação de Votação

A aplicação final simula um sistema de votação em tempo real, orquestrado com Kubernetes. Sua arquitetura é composta por:

-   **App de Votação (Frontend):** Interface web para registrar os votos.
-   **Redis:** Fila para armazenar os votos de forma rápida e temporária.
-   **Worker:** Serviço que processa os votos da fila e os consolida no banco de dados.
-   **Postgres:** Banco de dados relacional para armazenamento persistente dos resultados.
-   **App de Resultados:** Interface web para visualizar a apuração dos votos em tempo real.

### Como Executar o Projeto Final

1.  Navegue até o diretório `projeto-final-voting-app`.
2.  Certifique-se de que um `PersistentVolume` compatível está disponível no cluster (um exemplo está em `2-postgres/pv-pvc.yaml`).
3.  Aplique todos os manifestos no seu cluster:
    ```bash
    # Crie o namespace primeiro
    kubectl apply -f 1-namespace.yaml

    # Aplique todos os outros componentes
    kubectl apply -R -f .
    ```
4.  Verifique os serviços e acesse as `NodePorts` para visualizar a aplicação.

## 📚 Tecnologias e Conceitos Abordados

Durante este módulo, os seguintes tópicos foram estudados e aplicados:

-   **Fundamentos do Kubernetes:** Arquitetura, componentes (Master e Worker Nodes) e fluxo de trabalho.
-   **Ambiente e Configuração:** Uso de `kubectl`, arquivos de marcação (YAML) e gerenciamento de contextos.
-   **Cargas de Trabalho (Workloads):**
    -   `Pods` e `Namespaces` para isolamento e organização.
    -   `ReplicaSets` e `Deployments` para gerenciamento de implantações e escalabilidade.
    -   `DaemonSets` para garantir que um pod execute em todos os nós.
    -   `StatefulSets` para aplicações que exigem estado persistente.
-   **Rede e Descoberta de Serviços:**
    -   `Services` dos tipos ClusterIP, NodePort e LoadBalancer.
-   **Auto-scaling:**
    -   `Horizontal Pod Autoscaler (HPA)` para dimensionamento automático baseado em métricas.
-   **Configuração e Segurança:**
    -   `ConfigMaps` para externalizar configurações.
    -   `Secrets` para gerenciar dados sensíveis como senhas e chaves de API.
-   **Armazenamento:**
    -   `Volumes`, `PersistentVolumes (PV)` e `PersistentVolumeClaims (PVC)`.
    -   `ServiceAccounts`, `Roles` e `RoleBindings` para controle de acesso (RBAC).

## Agradecimentos

Agradeço à **Ada Tech**, **Gerdau** e ao instrutor **Wilton Guilherme** pela oportunidade e pelo aprendizado de alta qualidade.
