# Pacote e comandos

## Metadados e entrada publicada

- Nome: `@arapucajs/prettier`.
- Versão atualmente declarada: `1.1.0` (consulte sempre `package.json` para o valor vigente).
- Formato do pacote: ESM no manifesto, com ponto de entrada explicitamente CommonJS.
- Entradas: `main` e `exports["."]` apontam para `index.cjs`.
- Arquivos publicados: o campo `files` inclui `index.cjs` e `docs/`; npm também inclui arquivos padrão como `README.md`, `package.json` e a licença.
- Licença: MIT.

O arquivo exportado é um objeto de opções para o Prettier; não é executável de linha de comando.

## Dependências

`prettier` é uma dependência de desenvolvimento usada neste repositório para lint e formatação; consumidores precisam instalar sua própria versão do Prettier. Dependências de desenvolvimento também incluem Commitizen, Commitlint e Husky para convenções locais. Não há dependência de runtime declarada no manifesto atual e, portanto, o plugin EdgeJS não é instalado pelo pacote.

## Scripts

| Script       | Comando                               | Comportamento                                                         |
| ------------ | ------------------------------------- | --------------------------------------------------------------------- |
| `prepare`    | `husky install`                       | Inicializa hooks Git locais na instalação do projeto.                 |
| `lint`       | `prettier --check .`                  | Verifica formatação; não altera arquivos.                             |
| `format`     | `prettier --write .`                  | Reescreve os arquivos cobertos pelo Prettier.                         |
| `test`       | `echo "No tests specified" && exit 0` | Placeholder que sempre termina com sucesso; não valida comportamento. |
| `commit`     | `cz`                                  | Inicia o assistente Commitizen configurado no manifesto.              |
| `commitlint` | `commitlint --edit`                   | Invoca Commitlint; o hook `commit-msg` passa o caminho da mensagem.   |

O hook `.husky/pre-commit` executa `npm test`; como esse script é um placeholder, ele não funciona como validação de qualidade. O hook `.husky/commit-msg` executa Commitlint na mensagem do commit.

## Lockfiles

O repositório mantém `package-lock.json` e `bun.lock`. Alterações de dependências devem atualizar os dois arquivos e verificar que ambos resolvem o manifesto. Evite editar versões resolvidas manualmente.

## Publicação

O pacote declara `publishConfig.provenance: true`, links de repositório e metadados npm no manifesto. Confirme o estado real dos workflows e a configuração da organização antes de documentar um processo automatizado de publicação; este pacote não tem script `build` ou `release` declarado.
