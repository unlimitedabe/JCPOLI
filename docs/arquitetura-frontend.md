# Arquitetura frontend

## Visão geral

A versão da JCPOLI em que trabalhei era uma aplicação frontend desenvolvida principalmente com **Vue.js 2 e TypeScript**.

A aplicação utilizava uma estrutura baseada em:

- roteamento com Vue Router;
- views responsáveis pelas páginas;
- componentes Vue;
- models TypeScript;
- arquivos locais contendo os dados das edições;
- assets estáticos;
- separação de conteúdo por edição da JCPOLI.

Na versão final da minha participação, o conteúdo das diferentes edições não era carregado de um banco de dados externo.

As informações eram organizadas dentro da própria aplicação e carregadas de acordo com a edição acessada pelo usuário.

![Arquitetura frontend da JCPOLI](/assets/diagramas/arquitetura-frontend.drawio.svg)

---

# Stack principal

As principais tecnologias presentes na aplicação eram:

```text
Vue.js 2
TypeScript
JavaScript
Vue Router
Vuex
Sass
Vue CLI
```

Também estavam presentes bibliotecas de interface e suporte, como:

```text
Vuetify
Bootstrap Vue
Moment
Axios
VeeValidate
```

Neste estudo de caso, entretanto, o foco está nas tecnologias diretamente relacionadas às funcionalidades em que trabalhei.

---

# Estrutura geral

De forma simplificada, a navegação seguia este fluxo:

```text
Usuário
   │
   ▼
Vue Router
   │
   ▼
View
   │
   ▼
Identificação da edição
   │
   ▼
Componente correspondente
   │
   ▼
Model / arquivo de dados
   │
   ▼
Conteúdo exibido
```

A edição acessada pelo usuário determinava quais componentes e quais conjuntos de dados deveriam ser apresentados.

---

# 1. Entrada da aplicação

A aplicação Vue era inicializada a partir da estrutura tradicional do projeto:

```text
src/
├── main.ts
├── App.vue
├── router.ts
└── store.ts
```

## `main.ts`

Responsável pela inicialização da aplicação Vue e pelo carregamento dos principais recursos utilizados globalmente.

## `App.vue`

Funcionava como componente principal da aplicação.

Durante o desenvolvimento das múltiplas edições, esse arquivo também precisou ser adaptado para acompanhar a nova lógica de navegação.

## `router.ts`

Centralizava as definições de rotas.

Esse arquivo teve papel importante durante minha atuação, principalmente na transição entre:

```text
navegação por página
```

e

```text
navegação por edição + página
```

---

# 2. Roteamento

O Vue Router era responsável por associar URLs às diferentes views da aplicação.

Com apenas uma edição, uma rota poderia conceitualmente representar apenas a funcionalidade:

```text
/palestras
/minicursos
/competicoes
```

Com a inclusão do histórico das edições, a rota passou a precisar representar também o contexto da edição.

Conceitualmente:

```text
/:edicao/palestras
/:edicao/minicursos
/:edicao/competicoes
```

Isso permitia que a mesma categoria de página existisse em diferentes versões do evento.

Exemplo:

```text
1ª JCPOLI
└── Palestras

2ª JCPOLI
└── Palestras

3ª JCPOLI
└── Palestras
```

O roteamento passou, portanto, a funcionar como uma das principais formas de identificar qual conteúdo deveria ser apresentado.

---

# 3. Views

A pasta `views` concentrava as páginas acessadas diretamente pelo sistema de rotas.

Entre as views da JCPOLI estavam páginas relacionadas a:

```text
Home
Escola
Palestras
Minicursos
Competições
Exposições
Publicações
Orientações
Edições
Fotos
Ciência em Casa
Programação
Perfil de palestrante
```

Na versão independente da JCPOLI, os nomes das views foram simplificados.

Exemplo:

```text
PalestrasJCPOLI.vue
```

passou a ser:

```text
Palestras.vue
```

O mesmo processo ocorreu com outras páginas.

A remoção do sufixo tornou possível simplificar a estrutura após a decisão de separar novamente a JCPOLI do site da Escola Politécnica.

---

# 4. Views como pontos de entrada

Com múltiplas edições, a view não precisava necessariamente conter todo o conteúdo visual da página.

Ela podia funcionar como um ponto de entrada para componentes específicos da edição.

De forma conceitual:

```text
Palestras.vue
    │
    ├── PalestrasJ1.vue
    ├── PalestrasJ2.vue
    └── PalestrasJ3.vue
```

Ou:

```text
Escola.vue
    │
    ├── EscolaJ1.vue
    ├── EscolaJ2.vue
    └── EscolaJ3.vue
```

![Multiplas edições](assets/diagramas/estrutura-multiplas-edicoes.drawio.svg)

A edição presente na navegação determinava qual componente seria exibido.

Essa estratégia permitia manter uma única rota funcional para uma categoria de página e variar seu conteúdo conforme a edição selecionada.

---

# 5. Componentização

Grande parte do conteúdo visual estava organizada em componentes Vue.

A estrutura evoluiu para separar explicitamente os componentes por edição.

Exemplo:

```text
src/
└── components/
    └── abasJCPOLI/
        ├── 1_JCPOLI/
        │   ├── AnaisJ1.vue
        │   ├── CompeticaoJ1.vue
        │   ├── EscolaJ1.vue
        │   ├── ExposicoesJ1.vue
        │   ├── HomeJ1.vue
        │   ├── MinicursosJ1.vue
        │   ├── OrientacoesJ1.vue
        │   └── PalestrasJ1.vue
        │
        ├── 2_JCPOLI/
        │   ├── AnaisJ2.vue
        │   ├── CompeticaoJ2.vue
        │   ├── EscolaJ2.vue
        │   ├── ExposicoesJ2.vue
        │   ├── HomeJ2.vue
        │   ├── MinicursosJ2.vue
        │   ├── OrientacoesJ2.vue
        │   └── PalestrasJ2.vue
        │
        └── 3_JCPOLI/
            ├── AnaisJ3.vue
            ├── CienciaEmCasaJ3.vue
            ├── CompeticaoJ3.vue
            ├── EscolaJ3.vue
            ├── ExposicoesJ3.vue
            ├── FotosJ3.vue
            ├── HomeJ3.vue
            ├── MinicursosJ3.vue
            ├── OrientacoesJ3.vue
            └── PalestrasJ3.vue
```

Essa organização foi adotada durante a evolução do projeto para tornar explícita a relação entre cada componente e sua edição.

---

# 6. Componentes da Home

A página inicial também possuía componentes próprios para cada edição.

A estrutura foi organizada de forma semelhante:

```text
components/
└── home/
    ├── 1_JCPOLI/
    ├── 2_JCPOLI/
    └── 3_JCPOLI/
```

Dentro dessas pastas estavam componentes relacionados a elementos como:

```text
About
Carousel
Dates
```

Cada edição podia, portanto, possuir conteúdo e apresentação próprios sem exigir uma aplicação separada.

---

# 7. Dados da programação

Na versão em que trabalhei, uma parte significativa dos dados utilizados pelas páginas estava armazenada em arquivos TypeScript.

Esses arquivos ficavam principalmente em:

```text
src/storage/programacao/
```

A estrutura também foi organizada por edição:

```text
storage/
└── programacao/
    ├── 1_JCPOLI/
    ├── 2_JCPOLI/
    └── 3_JCPOLI/
```

Entre os tipos de conteúdo armazenados estavam informações relacionadas a:

```text
palestras
minicursos
competições
exposições
publicações
programação
Ciência em Casa
palestrantes
```

Um exemplo de nomenclatura utilizada era:

```text
palestras_new_1JCPOLI.ts
palestras_new_2JCPOLI.ts
palestras_new_3JCPOLI.ts
```

O mesmo princípio era aplicado a outros conteúdos.

---

# 8. Models TypeScript

A aplicação também possuía arquivos de model utilizados para estruturar determinados dados.

Entre os arquivos preservados estavam modelos como:

```text
miniCourses1JCPOLI.ts
miniCourses2JCPOLI.ts
miniCourses3JCPOLI.ts
speakersJCPOLI.ts
```

Esses arquivos ajudavam a manter uma estrutura definida para os dados utilizados pelos componentes.

Um fluxo típico podia ser representado como:

```text
Arquivo de dados
      │
      ▼
Model TypeScript
      │
      ▼
Componente Vue
      │
      ▼
Interface
```

---

# 9. Separação entre estrutura e conteúdo

Uma característica importante da solução era a separação entre:

```text
estrutura visual
```

e

```text
conteúdo da edição
```

Por exemplo, um componente responsável por apresentar uma palestra podia ser reutilizado enquanto os dados específicos eram recebidos de arquivos correspondentes à edição.

Conceitualmente:

```text
Componente de palestra
        │
        ├── dados da 1ª edição
        ├── dados da 2ª edição
        └── dados da 3ª edição
```

Essa separação aparece especialmente nas áreas relacionadas a palestras, minicursos e Ciência em Casa.

---

# 10. Componentes de Palestras e Minicursos

Algumas áreas utilizavam componentes mais genéricos para renderizar informações estruturadas.

Um exemplo importante é o conjunto:

```text
components/
└── miniCourse/
    ├── index.vue
    ├── miniCourse.ts
    └── miniCourse.css
```

Durante as etapas finais do projeto, esses arquivos foram modificados em conjunto para alterar a forma de apresentação das informações.

As alterações incluíram elementos como:

- imagem do palestrante;
- acesso ao perfil;
- informações da atividade;
- links de certificados.

Essa organização separava:

```text
template Vue
lógica TypeScript
estilos CSS
```

dentro da mesma funcionalidade.

---

# 11. Navegação

A navegação também evoluiu durante o projeto.

Durante a fase de integração entre os sites, existiam:

```text
NavBar.vue
NavBarJCPOLI.vue
```

Uma barra estava relacionada à estrutura geral da Escola Politécnica e a outra às páginas da JCPOLI.

Com a separação dos sites, essa estrutura deixou de ser necessária.

A navegação foi simplificada e a `NavBarJCPOLI.vue` pôde ser removida, concentrando a navegação relevante na estrutura independente da JCPOLI.

---

# 12. Responsividade

A navbar e a página de Edições precisaram de adaptações específicas para dispositivos móveis.

Durante a fase em que as duas navegações coexistiam, o comportamento mobile era particularmente complexo, pois era necessário acomodar:

```text
navegação da Escola
+
navegação da JCPOLI
```

Foram realizados ajustes na apresentação das opções de menu e na página utilizada para selecionar as edições.

---

# 13. Assets

A aplicação também possuía grande quantidade de conteúdo estático.

Entre os assets estavam:

```text
imagens de palestrantes
banners
logos
fotografias
editais
resultados de competições
publicações
arquivos PDF
```

Esses arquivos eram utilizados diretamente pelas diferentes edições.

Na 3ª JCPOLI, por exemplo, a área de Fotos exigiu a inclusão de dezenas de imagens utilizadas pela página correspondente.

---

# 14. Arquitetura simplificada

A arquitetura da minha versão pode ser representada desta forma:

```text
                    USUÁRIO
                       │
                       ▼
                 Vue Router
                 (router.ts)
                       │
                       ▼
                 Página / View
                       │
              identifica edição
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
       1_JCPOLI     2_JCPOLI     3_JCPOLI
          │            │            │
          ▼            ▼            ▼
      Componentes   Componentes   Componentes
          │            │            │
          ▼            ▼            ▼
        Dados        Dados        Dados
       TypeScript   TypeScript   TypeScript
          │            │            │
          └────────────┼────────────┘
                       ▼
                  Interface Vue
```

---

# 15. Arquitetura por responsabilidades

De maneira simplificada, cada camada tinha uma responsabilidade predominante:

| Elemento | Responsabilidade |
|---|---|
| `router.ts` | Definição das rotas e contexto de navegação |
| `views/` | Páginas acessadas pelo roteamento |
| `components/` | Estrutura e apresentação das funcionalidades |
| `components/abasJCPOLI/` | Componentes específicos de cada edição |
| `components/home/` | Componentes das páginas iniciais das edições |
| `models/` | Estruturas TypeScript utilizadas pelos dados |
| `storage/programacao/` | Conteúdo específico das edições |
| `public/assets/` | Imagens, documentos e demais arquivos estáticos |

---

# 16. Limitações arquiteturais

A solução utilizada durante minha participação possuía uma limitação importante: os conteúdos das edições eram mantidos dentro do próprio frontend.

Isso significa que uma atualização de conteúdo normalmente exigia:

```text
alterar arquivo
        ↓
versionar alteração
        ↓
gerar nova versão
        ↓
publicar aplicação
```

Uma solução baseada em backend ou CMS permitiria separar melhor a gestão de conteúdo do código da interface.

Esse tipo de evolução chegou a ser discutido no projeto, mas não fazia parte da implementação final da minha branch.

Por isso, este estudo de caso não apresenta banco de dados externo ou Firebase como parte da arquitetura desenvolvida por mim.

---

# 17. Decisão de organização por edição

Diante da ausência de uma fonte externa de dados, a organização por edição funcionou como uma forma de controlar a complexidade da aplicação.

Em vez de manter arquivos misturados:

```text
palestras1.ts
palestras2.ts
palestras3.ts
competicao1.ts
competicao2.ts
competicao3.ts
...
```

a estrutura passou a privilegiar:

```text
1_JCPOLI/
    conteúdo da 1ª edição

2_JCPOLI/
    conteúdo da 2ª edição

3_JCPOLI/
    conteúdo da 3ª edição
```

Essa decisão tornou mais explícita a relação entre cada arquivo e o contexto em que era utilizado.

---

# 18. Possível evolução arquitetural

Se a solução fosse evoluída atualmente, uma arquitetura possível seria separar os dados do frontend.

Conceitualmente:

```text
Frontend Vue
     │
     ▼
API / CMS
     │
     ▼
Banco de dados
```

As edições poderiam então ser representadas como entidades:

```text
Edição
├── palestras
├── palestrantes
├── minicursos
├── competições
├── exposições
├── publicações
└── demais conteúdos
```

Nesse modelo, a mesma interface poderia consumir dinamicamente qualquer edição cadastrada sem exigir novos arquivos TypeScript para cada evento.

Essa é uma evolução conceitual da arquitetura e não uma funcionalidade implementada durante minha atuação.

---

# Documentação relacionada

Para compreender como essa arquitetura surgiu ao longo do desenvolvimento:

➡️ [Evolução do projeto](evolucao-do-projeto.md)

Para ver especificamente as funcionalidades em que trabalhei:

➡️ [Minhas contribuições](minhas-contribuicoes.md)

Para consultar as evidências preservadas no Git:

➡️ [Evidências e histórico Git](evidencias.md)
