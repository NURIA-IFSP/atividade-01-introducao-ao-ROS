# Antes de começar!
### Como usar este repositório no GitHub Codespaces:

1. Crie uma conta gratuita no [GitHub](https://github.com).
2. (Opcional, mas recomendado) Cadastre-se no [GitHub Education](https://education.github.com/benefits) para acesso gratuito ao Codespaces.
3. Acesse o link abaixo para criar seu próprio Codespace:
   👉 [Criar Codespace](https://github.com/codespaces/new?template_repository=NURIA-IFSP/atividade-2-introducao-ao-ROS)


# Atividade 01 - introdução ao ROS

## Objetivos
- Conhecer o ambiente de desenvolvimento do ROS
- Executar um programa simples utilizando o turtlesim

## Como executar a simulação
1) Abrir o repositório da atividade no github
2) Executar o codespaces da atividade
3) Na primeira execução, após a criação do container no codespace podem ser necessários os comandos abaixo:

    - 3.0 Exibir o terminal no vscode com CTRL + J
    - 3.1 Abrir um novo terminal no vscode com o comando CTRL + J
    - 3.2 cd .devcontainer
    - 3.3 chmod +755 *.sh
    - 3.4 ./start-vnc.sh
    - 3.5) Clique em PORTAS e selecione a porta 6080 e apontando no link azul clique em abrir no navegador
    - 3.6 Quando a janela abrir no navegador clique em conectar
    - 3.7 Se necessário ajuste a resolução da tela para o seu monitor -Applications -> Settings -> Display, escolha a resolução e Apply
    - 3.8 Abra o vscode: Applications -> Development -> vscode

4) Abra o diretorio do exercicio -> atividade-01-introducao-ao-ROS
    - 4.1 - Abra no vscode os arquivos da aplicação: go_to_x.py , go_to_xy.py e simple_goal.py

5) Exiba os terminais, CTRL + J e crie um novo terminal
6) Compile o pacote
    - 6.1 cd catkin_ws
    - 6.2 catkin build
    - 6.3 source devel/setup.bash

7) Execute o programa principal num dos terminais: roslaunch pratica_ros_1 go_to_xy.launch
   Isto deverá exibir a janela do turtlesim.

8) No outro terminal execute o programa em python que define a posicao que a tartaruga deve se mover: rosrun pratica_ros_1 simple_goal.py

    - 8.1 - Entre com a posicao desejada conforme solicitado no prompt e veja a tartaruga se movimentar!
    - 8.2 - Repita o comando sempre que quiser movimentar a tartaruga para uma nova posicao

9) Para encerrar o programa, vá para o terminal que está rodando o lançador do programa e digite CTRL + C

DICA: para manter a tela do turtlesim sempre visivel, clique na barra de titulo com o botao direito e escolha a opção "Sempre no topo"
