# Projeto conversão de temperatura

### Sobre o projeto
O projeto conversão de temperatura é um projeto desenvolvido em NodeJS. O projeto tem como objetivo ser um exemplo para a criação de ambiente com containers usando NodeJS.

### Observações do projeto
A aplicação é exposta usando a porta 8080


#fazendo uso do docker commit para unir o containet ubunto + customizações (prerequisitos, aplicação) gerando uma nova imagem.

1 - docker container commit df844d3b96f9 conversao-temperatura
2 - docker container run -d -p 8080:8080 conversao-temperatura node /app/server.js

O comando a seguir é usado para executar um contêiner Docker com configurações específicas:

bash
Copiar código
docker container run -d -p 8080:8080 conversao-temperatura node /app/server.js
Abaixo está uma explicação detalhada de cada parte do comando.

1. docker container run
Este comando cria e inicia um contêiner baseado em uma imagem Docker.

docker: Chama o CLI do Docker.
container: Indica que o comando se refere a operações relacionadas a contêineres.
run: Cria e executa o contêiner.
2. -d
-d significa detached mode (modo em segundo plano).
O contêiner será executado em segundo plano, permitindo que você continue usando o terminal sem ficar preso à execução do contêiner.
3. -p 8080:8080
Este é o mapeamento de portas entre o host (máquina onde o Docker está rodando) e o contêiner.

8080 (antes dos dois pontos): Porta do host que será usada para acessar o serviço no contêiner.
8080 (depois dos dois pontos): Porta no contêiner onde a aplicação está escutando.
Esse mapeamento permite acessar o serviço rodando dentro do contêiner no endereço http://localhost:8080.
4. conversao-temperatura
Nome da imagem Docker que será usada para criar o contêiner.
A imagem deve estar disponível localmente ou em um registro Docker público/privado (como o Docker Hub).
5. node /app/server.js
Este é o comando que será executado dentro do contêiner após ele ser iniciado.

node: Executa o interpretador Node.js.
/app/server.js: Caminho do arquivo JavaScript (server.js) que será executado.
Geralmente, este arquivo contém o código do servidor da aplicação que está sendo executada dentro do contêiner.
Resumo do Comando
Este comando:

Inicia um contêiner em segundo plano com base na imagem conversao-temperatura.
Mapeia a porta 8080 do contêiner para a porta 8080 do host, permitindo acesso externo.
Executa o servidor Node.js localizado em /app/server.js dentro do contêiner.
Exemplo de Acesso
Se o servidor no arquivo server.js está configurado para escutar na porta 8080, você pode acessá-lo pelo navegador ou via curl no seguinte endereço:

plaintext
Copiar código
http://localhost:8080
Comandos Relacionados
Verificar se o contêiner está rodando:
bash
Copiar código
docker container ls
Parar o contêiner:
bash
Copiar código
docker container stop <container_id>
Verificar logs do contêiner:
bash
Copiar código
docker logs <container_id>
Com essa estrutura, você pode gerenciar e entender o que o comando está fazendo em cada etapa.