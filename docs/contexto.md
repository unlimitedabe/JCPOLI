# Contexto do projeto

## A JCPOLI

A **JCPOLI — Jornada Científica da Escola Politécnica e de Artes** é um evento acadêmico promovido no contexto da Pontifícia Universidade Católica de Goiás (PUC Goiás).

O evento reúne diferentes atividades acadêmicas e científicas e utilizava um site próprio para centralizar informações relacionadas às suas edições.

Entre os conteúdos disponibilizados estavam:

- palestras;
- minicursos;
- competições;
- exposições;
- publicações e anais;
- orientações;
- programação;
- informações de palestrantes;
- demais atividades relacionadas ao evento.

Durante minha atuação em 2024, estava sendo preparada a **3ª edição da JCPOLI**.

---

# Contexto da minha participação

Minha participação ocorreu durante o estágio supervisionado do curso de **Engenharia de Computação da PUC Goiás**, iniciado em março de 2024.

O trabalho foi realizado na área de desenvolvimento web e tinha inicialmente como principais objetivos:

- integrar o site da JCPOLI ao site da Escola Politécnica e de Artes;
- implementar melhorias na JCPOLI;
- atualizar as informações necessárias para a nova edição;
- trabalhar de maneira colaborativa utilizando Git e GitHub;
- documentar as alterações realizadas.

O desenvolvimento ocorreu sobre bases de código já existentes.

Portanto, minha atividade não consistiu em criar a JCPOLI do zero, mas em compreender, integrar, modificar e evoluir uma aplicação que já possuía histórico de desenvolvimento anterior.

---

# Situação inicial

Quando iniciei o trabalho, existiam dois contextos distintos:

```text
Site da Escola Politécnica e de Artes
                +
          Site da JCPOLI
```

O site da Escola Politécnica possuía sua própria estrutura de páginas e navegação.

A JCPOLI, por sua vez, possuía páginas específicas relacionadas ao evento, como:

```text
Home
Escola
Palestras
Minicursos
Competições
Exposições
Publicações
Orientações
```

O objetivo inicial era incorporar essa segunda estrutura à primeira aplicação.

---

# Problema inicial

A integração não consistia apenas em adicionar um link para outro site.

O conteúdo da JCPOLI precisava funcionar dentro da aplicação da Escola Politécnica.

Isso significava incorporar elementos como:

```text
rotas
views
componentes
navegação
assets
dados da programação
```

mantendo as funcionalidades necessárias para o evento.

Foi criada, por exemplo, uma área específica da JCPOLI dentro da aplicação e uma navegação própria para suas páginas.

---

# Evolução da necessidade

Após a integração inicial, surgiu uma necessidade adicional: preservar e disponibilizar o conteúdo das **edições anteriores da JCPOLI**.

Até então, o trabalho estava concentrado principalmente em trazer o conteúdo existente para a nova estrutura.

Com o histórico de edições, o problema passou a envolver também:

```text
1ª JCPOLI
2ª JCPOLI
3ª JCPOLI
```

Cada edição possuía informações próprias, como:

- palestrantes;
- palestras;
- minicursos;
- competições;
- exposições;
- publicações;
- datas;
- imagens;
- programação.

Foi então criada uma área de **Edições**, permitindo ao usuário selecionar qual edição desejava consultar.

---

# Restrição de dados

Na versão em que trabalhei, os conteúdos das edições não eram gerenciados por um banco de dados externo.

Grande parte dessas informações permanecia dentro da própria aplicação frontend.

Por isso, a inclusão das edições anteriores também representava um problema de organização do código.

Era necessário manter conteúdos diferentes dentro da mesma aplicação sem perder a relação entre:

```text
edição
   ↓
página
   ↓
componente
   ↓
dados
```

Essa restrição influenciou diretamente a organização adotada durante o projeto.

---

# Trabalho durante a 3ª JCPOLI

Com a aproximação e realização da 3ª edição, parte do trabalho passou a envolver também a manutenção das informações do evento.

Além das alterações estruturais, eram necessárias atualizações relacionadas a:

- palestras;
- minicursos;
- competições;
- resultados;
- publicações;
- orientações;
- Ciência em Casa;
- fotografias;
- certificados.

Isso adicionou ao projeto uma característica de manutenção de conteúdo durante um evento em andamento.

---

# Mudança de direcionamento

Durante o desenvolvimento ocorreu uma mudança importante de requisito.

A decisão inicial de manter a JCPOLI integrada ao site da Escola Politécnica foi revista após discussões entre as equipes envolvidas.

Foi decidido que os dois projetos deveriam continuar separados.

A situação mudou de:

```text
Escola Politécnica
        +
      JCPOLI
        ↓
 aplicação integrada
```

para:

```text
Escola Politécnica      JCPOLI
        │                  │
        ▼                  ▼
 aplicação própria     aplicação própria
```

Essa decisão tornou desnecessária parte da integração realizada anteriormente.

Entretanto, diversas melhorias desenvolvidas durante esse período ainda eram relevantes para a JCPOLI.

Entre elas:

- histórico das edições;
- nova estrutura de navegação;
- organização dos conteúdos;
- melhorias de layout;
- novas páginas;
- componentes das diferentes edições.

Por isso, o trabalho passou por uma nova etapa de reorganização.

---

# Nova configuração da JCPOLI

Após a separação, a aplicação voltou a ter a JCPOLI como seu único contexto.

Isso permitiu remover estruturas que haviam sido necessárias apenas para a convivência com o site da Escola Politécnica.

A versão passou a concentrar:

```text
JCPOLI
│
├── 1ª edição
├── 2ª edição
└── 3ª edição
```

com páginas e conteúdos específicos para cada uma.

Essa é a principal versão representada neste estudo de caso.

---

# Desenvolvimento colaborativo

O projeto não foi desenvolvido individualmente.

Durante o estágio, diferentes integrantes trabalhavam em atividades próprias e utilizavam branches distintas dentro dos repositórios da equipe.

Minhas principais branches foram:

```text
abe-juncaojcpolipolitecnica
abe-sitejcpoli-teste
```

A primeira está relacionada principalmente à fase de integração dos dois sites.

A segunda registra a continuidade do desenvolvimento após a decisão de manter a JCPOLI separada.

Este estudo de caso utiliza o histórico dessas branches e os commits associados ao meu usuário para distinguir minhas alterações do restante do projeto colaborativo.

---

# Escopo deste estudo de caso

Este repositório não pretende reconstruir toda a história da JCPOLI nem atribuir a mim o desenvolvimento completo do site.

O objetivo é documentar especificamente minha participação em 2024, principalmente nos seguintes problemas:

```text
integração de aplicações existentes
        ↓
evolução da navegação
        ↓
suporte a múltiplas edições
        ↓
organização de componentes e dados
        ↓
implementação da 3ª edição
        ↓
mudança de requisitos
        ↓
separação e reorganização da aplicação
```

A autoria das contribuições apresentadas é sustentada pelo histórico Git preservado e pelo relatório produzido durante o estágio.

---

# Documentação relacionada

Para conhecer especificamente as funcionalidades em que trabalhei:

➡️ [Minhas contribuições](minhas-contribuicoes.md)

Para acompanhar como o projeto mudou ao longo do estágio:

➡️ [Evolução do projeto](evolucao-do-projeto.md)

Para compreender a organização técnica da aplicação:

➡️ [Arquitetura frontend](arquitetura-frontend.md)

Para consultar a reconstrução baseada em commits e branches:

➡️ [Evidências e histórico Git](evidencias.md)