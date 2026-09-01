# Evidências e histórico Git

## Objetivo deste documento

A JCPOLI foi desenvolvida de forma colaborativa, com código produzido por diferentes estudantes ao longo de várias edições do projeto.

Por esse motivo, este estudo de caso não considera automaticamente todo o conteúdo do repositório como parte da minha autoria.

As contribuições apresentadas neste portfólio foram reconstruídas utilizando principalmente:

- o histórico Git preservado;
- commits associados ao meu usuário;
- minhas branches individuais;
- o relatório de estágio produzido durante o desenvolvimento;
- a cópia local recuperada do projeto.

O objetivo deste documento é registrar de forma transparente as principais evidências utilizadas para atribuir minhas contribuições.

---

# Identificação no histórico Git

Os commits relacionados à minha atuação aparecem principalmente associados ao usuário:

```text
unlimitedabe
```

e ao e-mail utilizado no projeto:

```text
unlimitedabe@gmail.com
```

O histórico recuperado contém dezenas de commits associados diretamente a esse usuário.

As duas principais branches utilizadas durante minha atuação foram:

```text
abe-juncaojcpolipolitecnica
abe-sitejcpoli-teste
```

Elas correspondem a duas fases diferentes do projeto.

---

# Branch `abe-juncaojcpolipolitecnica`

Essa branch foi utilizada durante a primeira etapa do trabalho.

O objetivo naquele momento era integrar o site da JCPOLI ao site da Escola Politécnica e de Artes.

Nela ficaram registradas alterações relacionadas a:

```text
integração das aplicações
rotas
navbar da JCPOLI
views
componentes
dados da programação
área de Edições
2ª edição da JCPOLI
responsividade
```

A branch preserva, portanto, a fase em que as duas aplicações estavam sendo transformadas em uma única solução.

---

# Branch `abe-sitejcpoli-teste`

Após a decisão de manter os sites separados, o desenvolvimento passou a continuar nesta branch.

Ela concentrou principalmente:

```text
JCPOLI novamente independente
estrutura de múltiplas edições
implementação da 3ª JCPOLI
reorganização dos componentes
reorganização dos dados
novas páginas
melhorias de interface
atualizações durante o evento
```

A versão final dessa branch foi posteriormente incorporada à linha principal do projeto.

---

# Critério de atribuição

Para este estudo de caso, considero uma alteração como evidência direta da minha participação quando existe pelo menos um dos seguintes elementos:

1. commit associado diretamente ao meu usuário;
2. alteração registrada em uma das minhas branches;
3. descrição correspondente no relatório de estágio;
4. combinação entre histórico Git e documentação produzida durante o estágio.

Funcionalidades existentes no projeto, mas sem evidência suficiente de autoria individual, são tratadas apenas como contexto do sistema.

---

# Commits representativos

Não é necessário apresentar todos os commits realizados durante o estágio.

Abaixo estão alguns dos que melhor representam a evolução técnica da minha participação.

---

## `a4d576c` — Adição inicial da JCPOLI

**Data:** 15/03/2024

```text
Adicionado aba jcpoli
```

Esse commit representa uma das primeiras etapas da integração da JCPOLI ao site da Escola Politécnica.

Ele marca o início da criação de uma área específica para o evento dentro da aplicação existente.

---

## `9c524e5` — Implementação da Home da JCPOLI

**Data:** 15/03/2024

```text
Implementado a pagina Home da JCPOLI
```

Foram adicionados elementos necessários para reproduzir a página inicial da JCPOLI, incluindo componentes relacionados a:

```text
About
Carousel
Dates
```

Esse commit faz parte da fase de incorporação da estrutura da JCPOLI ao outro site.

---

## `447cbc6` — Navbar específica da JCPOLI

**Data:** 16/03/2024

```text
Adicionada o navbar da jcpoli na aba jcpoli
```

Foi criada uma navegação própria para as diferentes áreas do evento.

Durante a fase de integração, a aplicação chegou a trabalhar simultaneamente com:

```text
NavBar.vue
NavBarJCPOLI.vue
```

permitindo separar a navegação geral da Escola Politécnica das páginas específicas da JCPOLI.

---

## Sequência de 17/03/2024 — Migração das páginas da JCPOLI

Diversos commits do mesmo período documentam a incorporação das principais áreas do site.

Entre eles:

```text
e65e00e — Escola
09b40f8 — Palestras
2768bbf — Minicursos
78204c4 — Competições
7111210 — Exposições
851a8e2 — Publicações / Anais
0c44d79 — Orientações
1cad773 — Programação
f4d9710 — Egressos
```

Esses commits mostram que a integração envolveu não apenas alterações de navegação, mas também views, rotas e arquivos contendo os dados utilizados pelas páginas.

---

# Área de Edições

## `4fd7a17` — Criação da aba Edições

**Data:** 31/03/2024

```text
Adicionado a aba de "Edições"
```

Esse commit marca o início da funcionalidade destinada ao histórico do evento.

---

## `2f660db` — Página e rotas de Edições

**Data:** 02/04/2024

```text
Adicionado rotas pra página de "Edições"
+ Layout da página de "Edições" da JCPOLI
```

A alteração envolveu:

```text
App.vue
NavBarJCPOLI.vue
router.ts
Edicoesj.vue
```

Foi criado o layout da página e sua integração ao sistema de rotas.

---

## `987cbe7` — Navegação pelos banners

**Data:** 03/04/2024

```text
Adicionado a função de router-link para os banners das edições
```

A página deixou de ser apenas uma apresentação visual e passou a funcionar como mecanismo de navegação entre as diferentes edições.

---

# Navegação por múltiplas edições

## `217793f` — Nova lógica de navegação

**Data:** 15/04/2024

Este é um dos commits mais representativos da minha atuação.

A alteração introduziu uma nova lógica para permitir que a aplicação identificasse:

```text
EDIÇÃO
   +
PÁGINA
```

Foram alterados simultaneamente:

```text
router.ts
App.vue
NavBar.vue
NavBarJCPOLI.vue
Edicoesj.vue
Jcpoli.vue
```

Também foram adicionados componentes relacionados à 2ª edição.

A nova estrutura permitia navegar conceitualmente entre caminhos como:

```text
1ª edição → Palestras
2ª edição → Palestras
3ª edição → Palestras
```

sem criar uma aplicação separada para cada edição.

Esse commit também introduziu a ideia de utilizar um componente Home específico para cada edição.

---

# Implementação da 2ª JCPOLI

Após a criação da nova estrutura de navegação, uma sequência de commits adicionou o conteúdo da segunda edição.

Entre eles:

```text
bf063da — Escola
b1bb999 — Palestras
1dee6b6 — Minicursos
c364c9f — Competições
049730e — Exposições
41352da — Publicações / Anais
ccf0152 — Orientações
```

Além das views e componentes, foram adicionados arquivos contendo os dados específicos da edição.

---

# Organização do código

## `39ff64f` — Separação dos arquivos da JCPOLI

**Data:** 03/05/2024

Esse commit iniciou uma reorganização importante da estrutura.

Foram criadas áreas próprias para arquivos da JCPOLI dentro de:

```text
components/home
models
storage/programacao
```

O objetivo era tornar mais clara a separação entre o conteúdo da Escola Politécnica e o conteúdo da JCPOLI durante o período em que os dois sites ainda estavam integrados.

---

# Responsividade

## `364d688` — Navegação mobile

**Data:** 10/05/2024

Foram realizados ajustes no comportamento mobile das barras de navegação.

A solução precisava lidar com a coexistência da navbar geral e da navbar específica da JCPOLI.

---

## `8688831` — Responsividade da página de Edições

**Data:** 10/05/2024

```text
Arrumado a responsividade da página de Edições
```

Esse commit registra ajustes específicos para melhorar a apresentação da nova página em diferentes tamanhos de tela.

---

# Implementação da 3ª JCPOLI

Entre 11 e 12 de maio foi adicionada grande parte do conteúdo da terceira edição.

Os commits incluem:

```text
c6ae3b3 — Home
6ea9bdf — Escola
698add8 — Palestras
ed89156 — Minicursos
3051173 — Competições
3aba90f — Exposições
08acb0d — Publicações / Anais
dab6d68 — Orientações
bdde76c — Ciência em Casa e Fotos
```

Esse conjunto mostra a implementação de praticamente toda a estrutura necessária para a nova edição.

---

# Ciência em Casa e Fotos

## `bdde76c`

**Data:** 12/05/2024

```text
Adicionado as abas de "Ciencia em Casa" e "Fotos" da 3 JCPOLI
```

Esse commit adicionou:

```text
CienciaEmCasaJ3.vue
FotosJ3.vue
views correspondentes
rotas
navegação
arquivo de dados de Ciência em Casa
assets da galeria
```

Também foram adicionadas dezenas de imagens utilizadas na área de Fotos.

---

# Mudança de requisito e separação dos sites

Em maio ocorreu uma mudança importante no projeto: a decisão de manter a JCPOLI e o site da Escola Politécnica como aplicações separadas.

O histórico Git permite acompanhar tecnicamente essa transição.

---

## `1b138e8` — Simplificação da navegação

**Data:** 12/05/2024

Entre as alterações:

```text
remoção da NavBarJCPOLI.vue
reorganização da NavBar.vue
alterações em App.vue
revisão das rotas
```

A existência de duas estruturas de navegação deixou de ser necessária.

---

## `ff7116e` — Remoção de elementos da Escola Politécnica

**Data:** 12/05/2024

Esse commit removeu diferentes partes que haviam sido herdadas do site da Escola Politécnica.

Entre elas estavam páginas, componentes e arquivos relacionados a:

```text
Home institucional
Hackathon
TCC
dados da Escola Politécnica
rotas que não pertenciam mais à JCPOLI
```

Esse é um dos commits que melhor representa tecnicamente a separação dos projetos.

---

## `d586b76` — Simplificação dos nomes das views

**Data:** 12/05/2024

Após a separação, nomes como:

```text
PalestrasJCPOLI.vue
EscolaJCPOLI.vue
CompeticaoJCPOLI.vue
```

deixaram de ser necessários.

As views foram renomeadas para:

```text
Palestras.vue
Escola.vue
Competicao.vue
```

entre outras.

Essa alteração também exigiu atualização da navbar e do roteamento.

---

# Organização definitiva por edição

## `a7c2067`

**Data:** 12/05/2024

Este é outro dos commits mais relevantes do histórico.

Uma grande quantidade de arquivos foi reorganizada para diretórios específicos:

```text
1_JCPOLI
2_JCPOLI
3_JCPOLI
```

A alteração afetou:

```text
components/abasJCPOLI
components/home
storage/programacao
views
```

Exemplo:

```text
components/abasJCPOLI/
├── 1_JCPOLI/
├── 2_JCPOLI/
└── 3_JCPOLI/
```

e:

```text
storage/programacao/
├── 1_JCPOLI/
├── 2_JCPOLI/
└── 3_JCPOLI/
```

Essa reorganização tornou explícita a relação entre os arquivos e a edição à qual pertenciam.

---

# Atualizações durante o evento

## `d9e10dd`

**Data:** 20/05/2024

Foram adicionados os resultados de competições realizadas durante a 3ª JCPOLI.

Isso incluiu documentos de resultados e atualização dos dados da programação.

---

## `6d8793b`

**Data:** 20/05/2024

```text
Adicionado botão de certificados na aba de "Palestras"
e "Ciencia em casa"
```

A alteração envolveu:

```text
component Vue
dados de Palestras
dados de Ciência em Casa
```

---

# Evolução da interface

## `02f5192`

**Data:** 07/06/2024

Outro commit especialmente representativo.

Foram alteradas as telas de:

```text
Palestras
Minicursos
Ciência em Casa
```

com inclusão de:

```text
foto do palestrante
acesso ao perfil
nova organização visual
informações de certificado
```

A alteração afetou diferentes partes da aplicação:

```text
index.vue
miniCourse.css
miniCourse.ts
models
storage/programacao
componentes Vue
```

Isso demonstra uma alteração coordenada entre apresentação, estilo, lógica e estruturas de dados.

---

# Consolidação da versão

## `2b8bbf3`

**Data:** 08/06/2024

Este é o último commit da branch:

```text
abe-sitejcpoli-teste
```

na versão recuperada.

Ele inclui ajustes finais, comentários e atualização da documentação.

---

## `edf96d7`

**Data:** 08/06/2024

O histórico registra posteriormente:

```text
Merge branch 'abe-sitejcpoli-teste':
ultima versão do projeto do site da JCPOLI,
atualizada por Abe.
```

Esse merge é uma evidência importante de que a versão produzida na minha branch foi incorporada à linha principal utilizada pela equipe.

---

# Evidências do relatório de estágio

Além do Git, o relatório produzido durante o estágio documenta as mesmas etapas de desenvolvimento.

O documento registra:

```text
integração entre os sites
criação da navbar
implementação das páginas da JCPOLI
propostas de layout
criação da área de Edições
suporte às edições anteriores
atualizações da 3ª JCPOLI
mudança de requisito
separação dos sites
reorganização do projeto
uso das branches individuais
```

A correspondência entre o relatório e o histórico Git fornece uma segunda fonte para reconstrução das atividades.

---

# O que não atribuo como contribuição individual

O repositório possui uma história anterior e posterior à minha participação.

Por isso, nem todas as funcionalidades e tecnologias presentes no código são apresentadas neste portfólio como trabalho realizado por mim.

Entre os exemplos está a integração com **Firebase**.

O histórico mostra commits relacionados a Firebase realizados por outros integrantes depois da consolidação da minha versão.

Por esse motivo, Firebase não é apresentado como parte da arquitetura desenvolvida por mim neste estudo de caso.

Da mesma forma, componentes e funcionalidades existentes antes da minha participação são utilizados apenas para explicar o contexto da aplicação quando necessário.

---

# Níveis de evidência

Para manter a documentação transparente, as informações deste case study podem ser divididas em três níveis.

## 1. Evidência direta

Existe commit identificado com meu usuário ou alteração registrada em minha branch.

Exemplos:

```text
roteamento por edição
área de Edições
organização por edição
Ciência em Casa
Fotos
ajustes de responsividade
evolução de Palestras e Minicursos
```

## 2. Evidência documental

A atividade está descrita no relatório de estágio produzido durante o desenvolvimento e é consistente com o histórico recuperado.

Exemplo:

```text
decisão de integrar os dois sites
mudança posterior para mantê-los separados
```

## 3. Contexto do projeto

A funcionalidade ou tecnologia existia no repositório, mas não há evidência suficiente para afirmar que foi implementada por mim.

Nesses casos, ela não é apresentada como contribuição individual.

---

# Conclusão

A combinação entre:

```text
relatório de estágio
        +
branches individuais
        +
histórico Git
        +
commits identificados
        +
código recuperado
```

permite reconstruir com boa precisão a minha participação no projeto.

O objetivo deste estudo de caso não é apresentar todo o sistema como desenvolvimento individual, mas demonstrar especificamente os problemas técnicos em que trabalhei e como minhas alterações evoluíram ao longo do estágio.

---

# Documentação relacionada

➡️ [Minhas contribuições](minhas-contribuicoes.md)

➡️ [Evolução do projeto](evolucao-do-projeto.md)

➡️ [Arquitetura frontend](arquitetura-frontend.md)