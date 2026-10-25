# Orientações para Claude e agentes de IA

As instruções canônicas estão em [AGENTS.md](./AGENTS.md). Comece pelo índice [docs/README.md](./docs/README.md) e leia as páginas relevantes antes de mudar arquivos.

Este repositório publica `@arapucajs/prettier`, um preset de configuração do Prettier. O pacote exporta opções CommonJS por `index.cjs`; não é um formatador independente nem uma CLI. A configuração inclui opções como `trailingComma`, `semi`, `singleQuote`, `quoteProps`, `bracketSpacing`, `arrowParens` e `printWidth`. A linha que carregaria `prettier-plugin-edgejs` está comentada e o plugin não aparece atualmente nas dependências declaradas.

## Documentação obrigatória

Crie ou atualize documentação detalhada na mesma tarefa sempre que qualquer parte do projeto for criada ou modificada, incluindo código, configuração, dependências, scripts, lockfiles, empacotamento, CI, exemplos e os próprios documentos.

- Coloque a documentação em `docs/` e registre cada página em `docs/README.md`.
- Explique comportamento real, fluxo, entradas, saídas, limites, compatibilidade e manutenção para humanos e IAs.
- Atualize README e exemplos quando o uso público ou os requisitos mudarem.
- Verifique as afirmações nos arquivos reais; não perpetue instruções sobre outro pacote.

Confira `package.json`, `index.cjs`, `README.md`, `.husky/`, workflows existentes e ambos os lockfiles. Não invente testes ou automações: `npm test` é atualmente um placeholder. Preserve CommonJS no ponto de entrada e use Conventional Commits.
