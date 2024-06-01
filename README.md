# Configuração e Otimização do Servidor NGINX   

        
O objetivo deste projeto é configurar e otimizar um servidor NGINX para funcionar como servidor web, proxy reverso e gateway de API.
As principais metas incluem a otimização de desempenho, implementação de HTTPS, configuração de regras de proxy reverso e gerenciamento de servidores web seguros.



## Etapas do Projeto

1.   Configurar o NGINX para atuar como servidor web para um site ou aplicativo.

2.   Definir regras de proxy reverso para direcionar o tráfego para diferentes serviços ou aplicativos.

3.   Implementar HTTPS com certificados SSL/TLS e Estabelecer políticas de segurança adequadas.

4.   Aplicar técnicas de otimização para melhorar o desempenho do NGINX.

5.   Documentar todas as configurações e decisões tomadas durante o projeto.


## Ferramentas :


* [Nginx](https://www.nginx.com/) - Web Servidor
* [Docker](https://www.docker.com/) - Container



## Instalando o NGINX

Instalação do NGINX
Primeiramente, você precisa instalar o NGINX. Em sistemas baseados em Debian/Ubuntu, você pode usar o seguinte comando:

![Insta NGINX](https://github.com/marcosf-cruz1980/NGINX/assets/146502505/b4a4aa5a-dbb4-4eef-803c-8a7b026e3a27)

### Arquivo de Configuração Principal (nginx.conf)

O arquivo de configuração principal (/etc/nginx/nginx.conf) controla a operação global do NGINX. Um exemplo de configuração básica pode ser:

Pode ser acessado pelo link do arquivo: https://github.com/marcosf-cruz1980/NGINX/blob/main/nginx.conf


### Configuração de um Site
Para configurar um site, você cria um arquivo de configuração no diretório /etc/nginx/sites-available/. Aqui está um exemplo de configuração para um site chamado microservicos como o link abaixo:

https://github.com/marcosf-cruz1980/NGINX/blob/main/microservicos



### Habilitar o Site
Para habilitar o site, crie um link simbólico do arquivo de configuração no diretório sites-available para o diretório sites-enabled:

>sudo ln -s /etc/nginx/sites-available/microservicos /etc/nginx/sites-enabled/


### Testar a Configuração e Recarregar NGINX

Antes de reiniciar o NGINX, é bom testar a configuração para verificar se há erros:

> sudo nginx -t

Se não houver erros, recarrege o NGINX para aplicar as mudanças:

> sudo nginx -s reload


### Proxy reverso

Neste exemplo utilizamos os termos /servico1 e /servico2 para direcionar para a pagina requerida em localhost:8001 e localhost:8002. O arquivo pode ser encontrado no link abaixo.

https://github.com/marcosf-cruz1980/NGINX/blob/main/proxyreverso


###  Balanceamento e otimização de servidores:

O arquivo de microservicos mostra como seria o comportamento de uma distribição de acessos no caso de utilizarmos apenas 2 servidores sem backup conforme link abaixo.
Utilizando o endereço localhost:8003 onde o próprio servidor realiza a tarefa de encaminhar para os servicos1 e servicos2.

https://github.com/marcosf-cruz1980/NGINX/blob/main/microservicos

### Certificado SSL

Para esta atividade foi gerado um certificado local, gerando os arquivos .crt e .key para que seja possivel acessar a pagina HTTP com o certificado de segurança HTTPS.

arquivo .crt
>https://github.com/marcosf-cruz1980/NGINX/blob/main/certificate/localhost.crt

arquivo.key
>https://github.com/marcosf-cruz1980/NGINX/blob/main/certificate/localhost.key

configuração de acesso SSL

>https://github.com/marcosf-cruz1980/NGINX/blob/main/SSL
















