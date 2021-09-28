# CI/CD
- O que é CI/CD

    Pratica combinada de entrega e integração continua. Essencial para produtividade em equipes com muitos desenvolvedores

    ![Untitled](imgs/cicd.png)

    - **C**ontinuous **I**ntegration
    - Automatizar o build e testes toda vez que desenvolvedores integram código ao repositório para garantir que este novo código não está quebrando build e nem falhando em testes
    - **C**ontinuous **D**elivery
        - "CD" se refere à entrega contínua e/ou à implantação contínua, conceitos relacionados e usados alternadamente às vezes. Em ambos os casos, se trata da automação de fases avançadas do pipeline, mas são usados às vezes separadamente para ilustrar o nível de automação presente.
- Ferramentas
    - [Jenkins](https://www.jenkins.io)
        - O que é?
            - Ferramenta de automatização open-source
            - Free
            - Pode automatizar a integração entre outras tarefas
            - Sua maior vantagem é a sua popularidade e quantidade de Plugins disponíveis
            - É desenvolvido em Java
            - Gerenciamento de usuários
            - Escala facilmente
            - Suporte a pipelines e arquivo declarativo (Jenkinsfile)
        - O que ele faz?
            - Executa processos de interação contínua( build, test, performance, tarefas necessárias para a a verificação do funcionamento do software)
            - Gera um relatório apresentando todos os passos executados
            - Realiza o processo de deploy de forma automatizada 
            </br></br>

    - GitHub Actions
        - O que é?
            - Orquestrador de workflow

            - Orientado a eventos

            - Possui plano Free limitado
        - O que faz?
            - Crie Actions no seu repositório

                - **Workflow**: É onde vamos descrever todo o processo de automação para podermos compilar, testar e fazer deploy do nosso sistema.

                - **Actions**: São tarefas que vamos utilizar dentro do workflow. Aqui que vamos definir o que realmente nosso workflow vai fazer.
                    
**Fontes:**

[O que é CI/CD](https://www.redhat.com/pt-br/topics/devops/what-is-ci-cd) - RedHat

[Undestanding GitHub Actions](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions) - github

---
# Docker, docker-compose e kubernetes

- Containers
    - O que é docker
        
        É uma tecnologia de containerização para criação e uso de containers Linux
        
    - Para que serve o docker
        
        Com o Docker, é possível lidar com os containers como se fossem máquinas virtuais modulares e extremamente leves. Além disso, os containers oferecem maior flexibilidade para você criar, implantar, copiar e migrar um container de um ambiente para outro
        
    - Porque usar docker
        - **Ambiente de execução:** Uma vez que sua aplicação seja transformada em uma imagem Docker, ela pode ser instanciada como container em qualquer ambiente que desejar. Isso significa que poderá utilizar sua aplicação no notebook do desenvolvedor da mesma forma que seria executada no servidor de produção.
        - **Aplicação como pacote completo:** Utilizando as imagens Docker é possível empacotar toda sua aplicação e dependências, facilitando a distribuição, pois não será mais necessário enviar uma extensa documentação explicando como configurar a infraestrutura necessária para permitir a execução, basta disponibilizar a imagem em repositório e liberar o acesso para o usuário e, ele mesmo pode baixar o pacote, que será executado sem problemas.
        - **Comunidade:** Usando o [repositório de imagens do Docker](https://hub.docker.com/) é possível conseguir bons modelos de infraestrutura de aplicações ou serviços prontos para integrações complexas.
        </br></br>
        
    - O que é docker-compose
        
        É uma ferramenta do docker para ajudar a definitir e compartilhar aplicações de vários contêineres. Com o Compose, você pode criar um arquivo YAML (docker-composer.yaml) para definir os serviços e executa-los com um único comando
        
    - Porque usar docker-compose
        - Todas as definições dos contêineres estarão em um único arquivo
        - Não há a necessidade explicita de configurar uma docker-network entre as aplicações do mesmo arquivo docker-composer
        - Facilita os testes, pois você estará trabalhando em ambientes muito próximos ao de execução
         </br></br>

- Container Orchestration
    - O que é kubernetes
        
        Com a popularização de contêineres, nasceu a necessidade de gerencia-los de forma automática. Por exemplo: Se um contêiner cair, outro precisa ser iniciado. É muito melhor que um sistema cuide desse comportamento.
        
        É ai que o Kubernetes (ou K8s) entra, no gerenciamento (ou orquestração) de ambientes com muitos contêineres, o que também é chamado de Cluster.
        
    - Porque usar kubernetes
        
        O kubernetes é capaz de escalonar, recuperar de falhas, fornecer padrões de implantações para seus contêineres.
        
        O Kubernetes oferece a você: 
        
        - **Descoberta de serviço e balanceamento de carga**
        O Kubernetes pode expor um contêiner usando o nome DNS ou seu próprio
        endereço IP. Se o tráfego para um contêiner for alto, o Kubernetes pode
        balancear a carga e distribuir o tráfego de rede para que a implantação
        seja estável.
         </br></br>
        - **Orquestração de armazenamento**
        O Kubernetes permite que você monte automaticamente um sistema de
        armazenamento de sua escolha, como armazenamentos locais, provedores de
        nuvem pública e muito mais.
         </br></br>
        - **Lançamentos e reversões automatizadas**
        Você pode descrever o estado desejado para seus contêineres implantados
        usando o Kubernetes, e ele pode alterar o estado real para o estado
        desejado em um ritmo controlada. Por exemplo, você pode automatizar o
        Kubernetes para criar novos contêineres para sua implantação, remover os contêineres existentes e adotar todos os seus recursos para o novo
        contêiner. </br></br>
        - **Empacotamento binário automático**
        Você fornece ao Kubernetes um cluster de nós que pode ser usado para
        executar tarefas nos contêineres. Você informa ao Kubernetes de quanta
        CPU e memória (RAM) cada contêiner precisa. O Kubernetes pode encaixar
        contêineres em seus nós para fazer o melhor uso de seus recursos.
         </br></br>
        - **Self-healing**
        O Kubernetes reinicia os contêineres que falham, substitui os
        contêineres, elimina os contêineres que não respondem à verificação de
        integridade definida pelo usuário e não os anuncia aos clientes até que
        estejam prontos para servir.
         </br></br>
        - **Gerenciamento de configuração e de segredos**
        O Kubernetes permite armazenar e gerenciar informações confidenciais,
        como senhas, tokens OAuth e chaves SSH. Você pode implantar e atualizar
        segredos e configuração de aplicações sem reconstruir suas imagens de
        contêiner e sem expor segredos em sua pilha de configuração.

Fontes: 

[O que é docker?](https://www.redhat.com/pt-br/topics/containers/what-is-docker) - RedHat

[Porque usar Docker?](https://stack.desenvolvedor.expert/appendix/docker/porque.html)

[What is Kubernetes?](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) - Kubernetes

---