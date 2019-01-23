# Instalação do servidor nginx no windows 10

Este é um resumo de como instalei o servidor opensource nginx 1.15.8
num windows 10.

  1. Baixe o servidor opensource do [site da nginx][31044170]

  [31044170]: nginx.org "NGINX"

  2. Descompacte o servidor num diretório tal que não haja espaços em branco no
     path até o diretório. Por exemplo, no Prompt do DOS:
     ```dos
     C:\Users\toto> unzip nginx-1.15.8.zip
     ```

  3. Configure o servidor.
     ```dos
     C:\Users\toto> cd nginx-1.15.8
     C:\Users\toto\nginx-1.15.8> notepad conf\nginx.conf
     ```

     Localize a linha:
     ```conf
             listen       80;
     ```
     No lugar da porta 80, usa-se a porta 8080 para não ter de rodar o
     servidor com direitos administrativos.
     As páginas ficam no subdiretório **html** debaixo do diretório onde foi
     descompactado o nginx.

  4. Execute o servidor
     Para rodar o servidor, no Prompt do DOS faça:
     ```dos
     C:\Users\toto\nginx-1.15.8> start nginx
     ```

  5. Teste o servidor
     Acesse a URL: [seu site local](http://localhost:8080/) no seu
     navegador de preferência.
     Você deve ver a página de saudação do NGINX.

  6.
