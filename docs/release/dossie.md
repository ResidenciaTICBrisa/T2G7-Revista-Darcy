# Interações do Projeto

## Introdução

O projeto foi conduzido pela equipe de desenvolvimento Brisa e pela equipe de design e editorial da Secom (Secretaria de Comunicação da UnB). Durante as diversas etapas do projeto, foram necessárias interações com a STI (Secretaria de Tecnologia da Informação) para questões como o ambiente de hospedagem do site e dúvidas sobre o processo de implantação. No entanto, houve posicionamentos que agravaram o desempenho do projeto, resultando na necessidade de alterações nos requisitos, adaptações no cronograma e mudanças no escopo. Este documento tem o objetivo de destacar as dificuldades enfrentadas durante o desenvolvimento do projeto.

## Descrição dos Processos

### Escopo Inicial

O escopo inicial do projeto envolvia o desenvolvimento de uma aplicação local WordPress utilizando o tema Gov.br produzido pelo IBCT. Na Release 1 do projeto, a versão inicial do site foi criada com este tema e plugins específicos para leitura dinâmica de PDFs e design das páginas.

### Problemas com Migração de Dados

Durante a migração do site, foi necessário utilizar um plugin chamado FGJoomla para a migração automatizada do conteúdo do site anterior para o novo site WordPress. No entanto, as tentativas de solicitação do acesso necessário ao banco de dados, essencial para a utilização do plugin, não tiveram sucesso pois a STI disponibilizou apenas o backup do site. A falta de acesso ao banco de dados levou à busca por soluções alternativas.

### Alterações no Escopo e Ambiente de Homologação

Quando se iniciou a tarefa de colocar o site em ambiente de homologação, surgiram novos problemas. A cliente solicitou por e-mail orientações sobre o processo de implantação em ambiente de homologação sendo posteriormente reforçadas pelo Product Owner, devido à demora na resposta da STI (devida à greve dos técnicos administrativos). A partir da resposta da STI, foi informado que o protótipo em desenvolvimento não teria suporte posterior se fosse produzido localmente, o que tornava inviável para o cliente essa abordagem, considerando que a equipe de desenvolvimento da Brisa tinha um prazo definido.

Como alternativa, a STI ofereceu um tema WordPress desenvolvido por eles, que permitiria à Secom obter suporte futuro da STI. No entanto, o modelo disponibilizado e o ambiente de homologação tinham restrições que impediam o desenvolvimento de certos requisitos. O time de desenvolvimento do Brisa possuia apenas acesso de Editor no ambiente WordPress o que restringia a instalação de plugins e alterações mais sensíveis.

### Restrições e Consequências

Após a mudança de escopo e a transição para o ambiente de homologação, foram feitas tentativas de instalar plugins para migração de dados, leitura de PDFs e instalação de fontes. No entanto, a solicitação da instalação do plugin por parte da STI não foi atendida.Segundo eles, as versões dos plugin não eram compartíveis com o tema e as versões compatíveis eram pagas. Como resultado, a migração teve que ser feita manualmente e o design não utilizou a fonte UnB Pro. 

Ao fazer solicitações para instalação de um plugin para leitura de PDF online, o plugin não possuía o mesmo comportamento que o que havia sido testado anteriormente. Questionando a STI sobre qual versão do plugin havia sido instalada não foi obtido resposta.

Portanto, o projeto sofreu diversas dificuldades durante o processo de desenvolvimento o que ocasionou em diversas mudanças e vários requisitos que dependiam desses plugins não puderam ser implementados por conta das restrições impostas.

