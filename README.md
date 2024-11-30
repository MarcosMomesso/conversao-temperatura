# Projeto conversão de temperatura

### Sobre o projeto
O projeto conversão de temperatura é um projeto desenvolvido em NodeJS. O projeto tem como objetivo ser um exemplo para a criação de ambiente com containers usando NodeJS.

### Observações do projeto
A aplicação é exposta usando a porta 8080


###
Criou-se uma imagem ubuntu docker, preparação da imagem + copia da aplicação e execução
docker container run -it -p 8080:8080 df844d3b96f9 /bin/bash
    docker start elated_dubinsky
    docker exec -it elated_dubinsky /bin/bash
instalado   node -> apt-get install -y nodejs 
            curl -> apt-get install -y curl
copiado a aplicação  --> docker container cp . df844d3b96f9:/app

executada a aplicação

1. docker container run
Esse é o comando base para criar e iniciar um contêiner a partir de uma imagem Docker.
2. -it
-i: Mantém o STDIN aberto, mesmo que você não esteja interagindo diretamente com o contêiner.
-t: Aloca um terminal pseudo-TTY, o que significa que você terá um terminal interativo dentro do contêiner.
Juntos, -it permite que você interaja com o terminal do contêiner (como se estivesse logado no sistema dentro do contêiner).

3. -p 8080:8080
Mapeia a porta 8080 do host (a máquina onde o Docker está sendo executado) para a porta 8080 dentro do contêiner.
Isso significa que qualquer serviço rodando na porta 8080 do contêiner ficará acessível pelo host na mesma porta.
4. df844d3b96f9
Esse é o ID da imagem Docker que será usada para criar o contêiner.
Esse ID é único para cada imagem e pode ser obtido com o comando docker images.
5. /bin/bash
Especifica o comando que será executado assim que o contêiner iniciar.
Neste caso, o comando /bin/bash inicia um shell interativo Bash dentro do contêiner.
O que acontece quando o comando é executado?
Um contêiner será criado e iniciado com base na imagem cujo ID é df844d3b96f9.
O terminal interativo do contêiner será aberto para que você possa interagir diretamente com ele.
Qualquer serviço ou aplicativo que escute na porta 8080 dentro do contêiner será acessível na porta 8080 do host.
Exemplo prático
Se a imagem contém uma aplicação web ou API que escuta na porta 8080, você pode acessá-la no navegador ou via curl no endereço http://localhost:8080.

Se não há nenhum serviço configurado na porta 8080, o comando apenas abre o terminal interativo do contêiner para que você possa executar comandos manualmente.