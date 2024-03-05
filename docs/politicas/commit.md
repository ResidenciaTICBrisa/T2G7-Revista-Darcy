---
tag: "politicas"
---
Padronização dos commits no projeto.

## Histórico de Versões


| Data       | Versão | Descrição                      | Autor             |
| :--------: | :----: | :----------:                   | :---------------: |
| 04/03/2024 |  0.1   | Criação da política de commits | [Joselito Prado](https://github.com/joselitopradomarques)|

## Semântica do Commit

Os commits devem seguir o seguinte padrão:

### Princípios:

#### Commits atômicos
Sempre dividir em pequenos e significativos commits, fazendo com que cada commit tenha apenas uma funcionalidade.

#### Commits em português
Por ser um projeto voltado totalmente para um público brasileiro e por toda equipe ter mais afinidade com o português, foi decidido que todos os commits serão em pt-BR.

### Formato:
```
(#número da issue): assunto
```

#### Assunto:

- Deve possuir no máximo 50 caracteres

*Exemplo de commit:*
```
git commit -m "(#02): botão na página inicial"
```

## Referências

DARTORA, João. Tudo o que você precisa saber sobre commits semânticos. *Ilegra*. Disponível em: <https://ilegra.com/blog/tudo-o-que-voce-precisa-saber-sobre-commits-semanticos/>. Acesso em: 04 de março de 2024.
