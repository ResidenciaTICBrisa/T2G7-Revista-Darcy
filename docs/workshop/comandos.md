# O que é o WordPress e como ele opera?

O WordPress é um sistema de gerenciamento de conteúdo (CMS - Content Management System) amplamente utilizado para criar e gerenciar sites e blogs. Ele é baseado em PHP e usa um banco de dados MySQL para armazenar conteúdo. O WordPress é conhecido por sua flexibilidade, facilidade de uso e uma grande comunidade de desenvolvedores e usuários que contribuem com plugins e temas.

# O que é o tema GovBR?

Uma solução open-source desenvolvida pela IBICT (Instituto Brasileiro de Informação em Ciência e Tecnologia) que visa facilitar a padronização da identidade visual do modelo Gov.BR para sites governamentais desenvolvidos em WordPress. O tema usa das tecnologias mais modernas do WordPress, incluindo os padrões de bloco do editor de páginas, além de oferecer integrações com alguns plugins comumente utilizados. 

**Linguagens utilizadas:** PHP, JavaScript, React, SCSS

## Por que ele foi criado?

### Motivo 1: Design System
Aplicações de governo precisam estar corretamente adequadas ao Design System do Portal Gov.BR, com padrões de interface que devem ser seguidos por designers e desenvolvedores para garantir a experiência única na interação com os sistemas interativos da Administração Pública Federal.

### Motivo 2: Preço e Acessibilidade
O Gov.BR utiliza o sistema de gestão de conteúdo Plone. No entanto, diversos sites governamentais utilizam o WordPress, um dos gerenciadores de conteúdo mais populares do mundo. Nesse sentido, alguns órgãos passam por desafios para adaptar seus sites e portais. O tema desenvolvido é uma alternativa para instituições que não podem usar o Plone.

Alguns órgãos governamentais, como a UnB, utilizam o Joomla como CMS padrão, no entanto, a dificuldade de manutenção e falta de intuitividade da plataforma fez surgir uma demanda de migração dos sites da Universidade para o WordPress. Ou seja, a necessidade de migração para o WordPress não é apenas da Revista Darcy, mas sim de todos os sites do domínio da Universidade de Brasília.

### Unindo o útil ao agradável
Dessa forma, sabendo a necessidade da migração dos sites governamentais para um CMS acessível e intuitivo como o WordPress, o IBICT criou o tema GovBR. Imagine a complexidade que seria se a cada novo site governamental, houvesse a necessidade de programadores para desenvolverem todo o front-end de acordo com o Design System do Governo Brasileiro. Por isso, instanciar o tema já produzido e evolui-lo de acordo com sua necessidade é o melhor caminho e também o mais rápido.

Hoje ensinaremos como você poderá iniciar o desenvolvimento de um site governamental localmente com o tema GovBR. Você aprenderá a instalar o WordPress, configurar o MySQL, iniciar um servidor local e conectar o tema GovBR a ele.

# Instalação no Ubuntu

## Passo 1: Instalação do XAMPP

O XAMPP é uma distribuição de software gratuita e de código aberto que facilita a instalação de um servidor web local. Ele é especialmente útil para desenvolvedores que precisam de um ambiente de desenvolvimento para testar e desenvolver websites e aplicações web localmente antes de colocá-las em produção. O XAMPP é uma distribuição Apache contendo MySQL, PHP, and Perl

https://www.apachefriends.org/download.html

1. Clicar em XAMPP for Linux - 8.0.30 / PHP 8.0.30 - Download (64 bits)
2. Abra os downloads do navegador e clique em “Mostrar na Pasta”
3. Clique com o botão direito no arquivo instalador do XAMPP e clique em “Propriedades” e após em “Permissões”.
4. Aperte em “Permitir execução do arquivo como um programa” e feche a tela.
5. Abra a pasta de downloads no terminal do Ubuntu. (Clicar no vazio com o botão direito e clicar em “Abrir no Terminal”)
6. Mude as permissões do instalador:

    ```bash
    chmod 755 xampp-linux-*-installer.run
    ```

7. Rode o instalador:

    ```bash
    sudo ./xampp-linux-*-installer.run
    ```

8. Após, irá abrir a tela de instalação. Conclua a instalação apertando em “avançar”.
    - *(Se em algum momento alguém fechar o launcher do XAMPP, rode:*

        ```bash
        sudo /opt/lampp/manager-linux-x64.run
        ```

    - *Lembrando que o Apache roda na porta 80, se alguém tiver problema na hora de inicializar, pode ser que tenha algum serviço rodando na porta 80, terá que derrubá-lo.*

## Passo 2: Configuração do XAMPP

1. Com o Launcher do XAMPP aberto, clique em “Manage Servers”.
2. Dê start nos servidores MySQL Database e Apache Web Server. O status dos dois deve estar como “Running”. O servidor ProFTPD pode estar desligado.
3. Verifique se o servidor Apache já está disponível em [http://localhost/](http://localhost/).

## Passo 3: Criação do Banco de Dados

1. No servidor local, disponível em [http://localhost/](http://localhost/), clique em “phpMyAdmin”, no canto superior direito da tela.
2. Crie um banco de dados novo, clicando em “Novo”, no canto superior esquerdo da tela.
3. Crie um nome pro seu banco de dados, não pode conter números e nem caracteres especiais, e tem que ser tudo minúsculo. Por exemplo: `govbr`. Agora clique em criar.
4. Pronto, agora o banco de dados está criado. Só falta uma coisa pro WordPress funcionar: os arquivos do WordPress.

## Passo 4: Instalando o WordPress

1. Acesse [https://br.wordpress.org/download/](https://br.wordpress.org/download/) e clique em “Download WordPress 6.5.5”.
2. Isso baixará um zip, que você deverá manualmente mover para a pasta do XAMPP.
3. Rode:

    ```bash
    sudo mv ~/Downloads/wordpress-6.5.5-pt_BR.zip /opt/lampp/htdocs/
    ```

4. Extraia o zip com o comando:

    ```bash
    sudo unzip /opt/lampp/htdocs/wordpress-6.5.5-pt_BR.zip -d /opt/lampp/htdocs/
    ```

5. Agora temos os arquivos do WordPress no local correto, dentro de `htdocs`. Também temos o banco de dados criado, no entanto, essas duas coisas ainda não se conhecem.

## Passo 5: Configurando o LocalHost

1. Acesse [http://localhost/wordpress/](http://localhost/wordpress/).
2. Estamos na tela de configuração do WordPress, clique em “Vamos lá”.
3. Em “Nome do banco de dados” insira o nome colocado no Passo 3, que no exemplo foi “govbr”.
4. Em “Usuário” escreva “root”.
5. Em “Senha” deixe vazio.
6. Servidor e prefixo deixe como está e clique em enviar.
7. Se aparecer um erro de permissão que diz “Não foi possível gravar dados no arquivo wp-config.php”, siga os passos abaixo:
    1. Volte pra tela anterior do WordPress.
    2. Abra o terminal e rode:

        ```bash
        sudo chmod -R 777 /opt/lampp/htdocs/wordpress
        ```

    3. Volte até a tela do WordPress no localhost e tente enviar novamente.
8. Agora, provavelmente, abriu outra tela de sucesso. Clique em “instalar”.
9. Coloque o título do site, como por exemplo “Teste Gov BR”.
10. Crie um nome de usuário, uma senha e insira seu email.
11. Clique em “Instalar o WordPress”.
12. Agora, você deve estar em uma tela de Sucesso. Clique em “Acessar”.

## Passo 6: Download e Ativação do Tema GovBR

1. Acesse o repositório do tema no GitHub: [https://github.com/IBICT/wp-govbr-tema](https://github.com/IBICT/wp-govbr-tema).
2. Clique em “Releases” no lado direito da tela.
3. Baixe o arquivo `govbr.zip`.
4. Abra o terminal e rode:

    ```bash
    sudo mv ~/Downloads/govbr.zip /opt/lampp/htdocs/wordpress/wp-content/themes/
    ```

5. Navegue até a página de temas:

    ```bash
    cd /opt/lampp/htdocs/wordpress/wp-content/themes/
    ```

6. Descompacte o tema que está zipado:

    ```bash
    sudo unzip govbr.zip
    ```
    
7. Volte ao seu site no WordPress e atualize a página de temas. O tema GovBR já deve aparecer disponível pra ser utilizado.
8. Clique em “ativar” o tema.

## Considerações Finais

Agora o WordPress está instalado, configurado e pronto para uso com o tema GovBR. A partir desse ponto, o desenvolvedor tem a possibilidade de editar o tema apenas no WordPress, abstraindo a complexidade da codificação de cada feature. Mas, caso haja a necessidade, ele poderá alterar o código apenas editando o já existente no arquivo do tema, com qualquer IDE ou Editor de Texto, como o VSCode, e poderá acompanhar as alterações em tempo de execução, uma vez que estiver com o servidor local do WordPress rodando.

