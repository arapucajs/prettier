# Opções exportadas

O ponto de entrada `index.cjs` exporta um objeto CommonJS de opções consumido pelo Prettier. Esta referência espelha os valores definidos no arquivo.

| Opção            | Valor          | Efeito                                                                                       |
| ---------------- | -------------- | -------------------------------------------------------------------------------------------- |
| `trailingComma`  | `"es5"`        | Adiciona vírgulas finais onde a sintaxe ES5 permite.                                         |
| `semi`           | `false`        | Omite ponto e vírgula ao final de instruções quando possível.                                |
| `singleQuote`    | `true`         | Prefere aspas simples em strings JavaScript quando isso não exige mais escapes.              |
| `useTabs`        | `false`        | Usa espaços para indentação.                                                                 |
| `quoteProps`     | `"consistent"` | Aplica aspas de forma consistente às propriedades de objetos conforme as regras do Prettier. |
| `bracketSpacing` | `true`         | Insere espaços dentro de chaves de objetos impressos, por exemplo `{ foo: bar }`.            |
| `arrowParens`    | `"always"`     | Inclui parênteses ao redor do parâmetro de funções arrow, inclusive com um parâmetro.        |
| `printWidth`     | `100`          | Define a largura de linha preferida para decisões de quebra; não é um limite rígido.         |

## Plugin EdgeJS

`index.cjs` contém uma linha comentada de configuração `plugins` para `prettier-plugin-edgejs`. Como está comentada e o pacote não declara o plugin como dependência de runtime, ela não participa da configuração exportada. Descomentar essa linha sem adicionar e validar a dependência no pacote consumidor pode fazer a resolução falhar.

## Alterações

Ao alterar uma opção, atualize esta tabela e exemplos pertinentes no mesmo commit. O código é a fonte de verdade para valores; valide nomes e valores permitidos contra a versão de Prettier suportada pelo pacote.
