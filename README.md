# @arapucajs/prettier

Preset compartilhado de opções do [Prettier](https://prettier.io/) usado nos pacotes e aplicações da ArapucaJS.

[![npm version](https://img.shields.io/npm/v/%40arapucajs%2Fprettier)](https://www.npmjs.com/package/@arapucajs/prettier)
[![license](https://img.shields.io/github/license/arapucajs/prettier)](./LICENSE)

## Instalação

Instale o Prettier e o preset como dependências de desenvolvimento do projeto consumidor:

```sh
npm install --save-dev prettier @arapucajs/prettier
```

Ou com Bun:

```sh
bun add -D prettier @arapucajs/prettier
```

## Configuração

No `package.json` do projeto:

```json
{
  "prettier": "@arapucajs/prettier"
}
```

Execute o formatador instalado no projeto:

```sh
npx prettier --check .
npx prettier --write .
```

## Opções incluídas

O preset configura:

- vírgulas finais no estilo `es5`;
- sem ponto e vírgula;
- aspas simples;
- indentação com espaços;
- aspas de propriedades consistentes;
- espaços dentro de chaves;
- parênteses sempre em parâmetros de arrow functions;
- largura preferida de linha de 100 caracteres.

Veja [a referência das opções](docs/references/options.md) para detalhes e valores exatos.

## Templates EdgeJS

O pacote atualmente **não instala nem habilita** `prettier-plugin-edgejs`. A configuração do plugin em `index.cjs` está comentada e o plugin não é uma dependência do pacote. Para formatar templates Edge, instale e configure um plugin compatível diretamente no projeto consumidor.

## Desenvolvimento neste repositório

```sh
npm install
npm run lint
```

`npm test` é atualmente um placeholder e não executa uma suíte de testes. Consulte a [documentação do projeto](docs/README.md), especialmente o [guia de instalação e uso](docs/guides/installation-and-usage.md) e a [referência de scripts e pacote](docs/references/package-and-commands.md).

## Contribuição

Atualize a documentação em `docs/` na mesma alteração sempre que modificar código, opções, dependências, scripts, empacotamento ou compatibilidade. Use Conventional Commits; `npm run commit` inicia o assistente Commitizen.

## Licença

MIT. Consulte [LICENSE](LICENSE).
