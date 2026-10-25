# Instruções para agentes — @arapucajs/prettier

Leia este arquivo e o índice [docs/README.md](docs/README.md) antes de alterar o repositório. O código, os manifests, os dois lockfiles, os workflows e a documentação são fontes de verdade; em caso de divergência, confirme o comportamento no código e corrija a documentação na mesma alteração.

## Escopo real

Este repositório publica `@arapucajs/prettier`, um preset compartilhado de configuração para o Prettier. O ponto de entrada publicado é `index.cjs`, um módulo CommonJS que exporta opções do Prettier. O pacote não é o próprio formatador, não contém CLI, não tem testes de aplicação e não oferece integração EdgeJS ativa atualmente.

## Documentação obrigatória

É obrigatório criar ou atualizar documentação detalhada sempre que algo novo for criado ou qualquer parte do projeto for modificada: configuração exportada, API, testes, exemplos, dependências, scripts, build/empacotamento, CI, instruções de agentes e documentação. Conclua essa atualização na mesma tarefa.

- Explique propósito, fluxo de uso, entradas, saídas, limites e manutenção para humanos e agentes de IA.
- Organize documentos em `docs/` e registre cada página em `docs/README.md`.
- Mantenha guias, referências, arquitetura, planejamento e ferramentas proporcionais ao escopo; não crie páginas vazias ou especulativas.
- Atualize o README quando instalação, configuração exportada, compatibilidade ou exemplos mudarem.
- Confira cada afirmação e exemplo em `package.json`, `index.cjs`, lockfiles e workflows disponíveis.

## Antes de alterar

1. Leia o índice `docs/README.md` e as páginas relevantes.
2. Inspecione `package.json`, `index.cjs`, `README.md`, `commitlint.config.js`, `.husky/`, workflows e os dois lockfiles.
3. Preserve o formato de módulo CommonJS e o contrato de exportação esperado pelo Prettier.
4. Não afirme que o pacote instala ou ativa `prettier-plugin-edgejs`: confirme primeiro a dependência de runtime e a configuração efetiva em `index.cjs`.
5. Não invente scripts, testes, arquivos de configuração, engines, CI ou requisitos não declarados.
6. Mantenha `package-lock.json` e `bun.lock` coerentes com o manifesto quando dependências mudarem.

## Comandos e convenções

Confirme os scripts em `package.json`. Atualmente `npm run lint` executa `prettier --check .`, `npm run format` executa `prettier --write .`, `npm test` é apenas um placeholder sem suíte de testes e `npm run prepare` inicializa Husky. Use Conventional Commits. Preserve alterações preexistentes e nunca inclua credenciais.
