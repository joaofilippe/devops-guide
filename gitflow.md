# GitFlow

## Branch Naming

**Long-Running Branches**:

São as branchs que possuem tempo de vida permanente no código. São branchs caracterizadas por sua perenidade.

Elas irão indicar os ambientes de desenvolvimento do código, podendo ser classificadas em estáveis e não estáveis.

A principal é a `main/master`, da qual se deverivam a `homologation/staging` e a `developer`.

Essas branches também serão caracterizadas por um nível maior de proteção. Em especial, a possibilidade de serem alteradas exclusivamente por meio de `Pull Requests`.

- **Main/Master**:
  - Será uma branch com uma versão estável do código;
  - Frequentemente estará atrás da branch `staging`;
  - É a versão que estará em produção;
- **Homologation**:
  - Será uma branch com uma versão estável do código;
  - Estará a frente da `main/master`;
  - Apenas features aprovadas poderão estar presentes na branch;
  - Estará no ambiente de produção para testes;
- **Developer**:
  - Será uma branch com uma versão menos estável do código;
  - Será responsável por conter uma ou mais features em estado de teste;
  - O ambiente de testes será simulado;

**Short-Lived Branches**:

São branchs com um tempo de vida definido. Seu ciclo de vida é não perene, devendo sempre ser excluídas após atingido seus respectivos objetivos.

Em sua essência, não são responsáveis por representar nenhum ambiente.

Diferentemente das branches `long-running`, elas serão atualizadas via *commits* diretos e via merge.

Serão caracterizadas pela sua não proteção em relação a modificações.

- **Hotfix**:
  - Criada a partir da branch `master/main`;
  - O objetivo é corrigir um erro em produção;
  - A correção deverá ser replicada para as branches `homologation` e `developer` após a finalização;
- **Bugfix**:
- **Features**:

*caso o idioma escolhido seja o portugues* As branchs deverão ser iniciadas com o nome do propósito da branch.

*caso idioma escolhido seja o inglês*.

## Conventional Commits

Links para consulta:

- <https://www.conventionalcommits.org/en/v1.0.0/>;
- <https://www.freecodecamp.org/news/writing-good-commit-messages-a-practical-guide/>;

Para facilitar a comunicação, o.

| Prefix | Use case |
|:-------|---------:|
|**feat**| Nova funcionalidade no código|
|**fix**| Correção em relação ao commit anterior|
|**refactor**| Refatoração de uma parte do código|
|**style**| Mudança no estilo do código|
|**test**| Tudo relacionado a realização de testes|
|**docs**| Tudo relacionado a documentação|
|**chore**| Tudo relacionado à manutenção do código|

### Exemplos de commits

```text
- feat: altera a cor do botão
- feat: insere nova validação do e-mail
```

```text
- fix: quebra de linha na seção de produtos
- fix: não envio de e-mail
```

```text
- style: ajustando espaçamentos na validação de e-mail
- style: corrigindo nome de variáveis 
```

```text
- refactor: removendo código duplicado
- refactor: mudando método A para a classe X
```

```text
- test: novo teste para cálculo do preço
- test: correção de falha de teste no registro da compra
```

```text
- docs: adicionar a documentação para o método de ordenação
- docs: corrigir a ortografia
```

```text
- chore: atualização da biblioteca
- chore: configuração do Jenkis
```

- Importante observar que somente commits com prefixos `feat` ou `fix` irão representar alterações nas funcionalidades do aplicativo;
- Os demais prefixos não podem alterar nenhuma funcionalidade do código, caso eles o façam, é um grande indicativo que o commit não está suficientemente localizado em funcionalidade específica do código.
