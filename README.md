
# Design Tokens Tools (DTT)

**DTT** é um conjunto de ferramentas modulares para transformar e integrar design tokens em múltiplos formatos como TypeScript, CSS custom properties e JSON.

Projetado como uma engrenagem de um ecossistema maior, o DTT impulsiona consistência, performance e integração entre times de design e desenvolvimento.

Este monorepo segue o princípio de responsabilidade única: tudo relacionado à geração, transformação e integração de design tokens vive aqui — seja aplicação web, CLI, microfrontend ou integrações futuras.

Ferramenta open-source para transformar arquivos JSON contendo design tokens em múltiplos formatos como TypeScript, CSS custom properties e JSON. O objetivo principal é melhorar a DX para projetos com Design Systems reutilizáveis e integrados.

Este monorepo segue o princípio de responsabilidade única: tudo relacionado à geração de tokens vive aqui — seja aplicação web, CLI ou microfrontend.

---


---

## ✨ Manifesto DTT

Design Tokens Tools não é apenas um gerador. É uma engrenagem fundamental em um motor maior de consistência e qualidade.

Acreditamos que design tokens são a linguagem universal entre design e código. Eles não são apenas variáveis — são **contratos vivos** entre intenção e entrega.

Criamos o DTT para:

- **Conectar mundos:** unificar design, código e documentação em uma estrutura comum
- **Promover consistência:** garantir que a identidade visual seja declarada de forma padronizada e confiável
- **Aumentar a performance:** reduzir retrabalho com geração automatizada de estruturas reutilizáveis
- **Declarar qualidade:** transformar tokens em código com tipagem, validação e clareza

**DTT** é mais que uma ferramenta. É a base de uma sinergia declarada entre contextos.


## 🚀 Roadmap

### Fase 1 – MVP funcional (App Web)
> Objetivo: Ferramenta visual simples para gerar TypeScript a partir de um JSON com tokens.

- [ ] Setup do projeto com Vite + React + TypeScript (`packages/app`)
- [ ] Configuração do TailwindCSS
- [ ] Página única com layout básico
- [ ] Componente de input (upload ou textarea para JSON)
- [ ] Validação de estrutura do JSON com Zod
- [ ] Conversão para arquivo `.ts` via `core`
- [ ] Visualização do código gerado (`<pre>` ou live preview)
- [ ] Botão para download do arquivo gerado
- [ ] UX simples e responsiva

---

### Fase 2 – Modularização com `core`
> Objetivo: Isolar a lógica de transformação em um pacote reutilizável.

- [ ] Criar `packages/core` com função pura de transformação (`json -> ts`)
- [ ] Tipar com rigor as entradas e saídas
- [ ] Exportar utilitários reutilizáveis (ex: gerador de nome de arquivo, flatten, etc.)
- [ ] Adicionar testes unitários ao core
- [ ] Aplicar core tanto no app web quanto no CLI

---

### Fase 3 – CLI para terminal
> Objetivo: Gerar tokens via linha de comando, sem depender da interface.

- [ ] Criar `packages/cli` como pacote binário (`design-tokens-tools`)
- [ ] Aceitar argumentos como `--input`, `--output`, `--format`
- [ ] Utilizar o `core` internamente
- [ ] Permitir integração com `npm scripts` (ex: `"generate:tokens": "tokens-generator"`)
- [ ] Adicionar opção de preset (ex: Tailwind, Chakra)
- [ ] Suporte a múltiplos formatos: `ts`, `json`, `css`, `scss`

---

### Fase 4 – Integração com documentação da lib
> Objetivo: Incorporar o gerador de tokens na doc-site da biblioteca de componentes.

- [ ] Adaptar a UI do `app` para se alinhar ao design system da doc
- [ ] Criar versão leve para embutimento (consumindo `core`)
- [ ] Publicar como pacote ou exportar visualmente via integração
- [ ] Garantir modo light/dark sincronizado
- [ ] Testar integração contínua entre lib e gerador

---

### Fase 5 – Microfrontend real (sem iframe)
> Objetivo: Exportar o gerador como microfrontend integrável via Module Federation.

- [ ] Criar `packages/mfe` com a versão do app exportável como remote
- [ ] Configurar Webpack Module Federation para expor `TokensGeneratorApp`
- [ ] Garantir isolamento de estilo com Tailwind ou CSS Modules
- [ ] Publicar de forma independente (Netlify, Vercel etc.)
- [ ] Permitir consumo remoto no doc-site: `import('tokens-generator/mfe/TokensGeneratorApp')`
- [ ] Documentar um exemplo de integração

---

### Fase 6 – Expansões e melhorias DX
> Objetivo: Tornar a ferramenta mais flexível e pronta para produção.

- [ ] Adicionar histórico recente no `localStorage`
- [ ] Adicionar suporte a temas (light/dark/presets)
- [ ] Internacionalização (pt-BR / en-US)
- [ ] Configuração por arquivo `.tokensgenrc` (CLI)
- [ ] Suporte futuro a plugin system (por exemplo: Figma import)

---

## 🏷 Labels sugeridas para issues

- `feature`
- `refactor`
- `bug`
- `infra`
- `cli`
- `app`
- `mfe`
- `enhancement`
- `doc`

---

## 🧱 Estrutura do Monorepo (Workspaces)

```
packages/
├── core/   # Lógica pura de transformação de tokens
├── cli/    # CLI binário para uso em projetos
├── app/    # Aplicação React com UI visual
└── mfe/    # Microfrontend exportável via Module Federation
```

---

## 🛠 Tecnologias

- React + TypeScript
- TailwindCSS
- Zod
- Vite / Webpack 5 (MF)
- pnpm (workspaces)

---

## 📄 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).
