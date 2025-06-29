# @arapucajs/prettier

<hr>
<br />

<div align="center">
  <h3>Configuração base do Prettier</h3>
  <p>Regras base do Prettier utilizadas pela equipe do ArapucaJS para pacotes e aplicações.</p>
</div>

<br />

<div align="center">

[![npm-image]][npm-url] [![license-image]][license-url]

</div>

## Instalação

Instale o pacote a partir do registro npm.

```sh
bun add -D @arapucajs/prettier

# Certifique-se também de instalar os seguintes pacotes
bun add -D prettier
```

## Uso

Após a instalação, você pode copiar/colar o bloco de código abaixo dentro do arquivo `package.json`.

```json
{
  "prettier": "@arapucajs/prettier"
}
```

Nossa configuração base também instala e configura o pacote [prettier-plugin-edgejs](https://github.com/sajansharmanz/prettier-plugin-edgejs) para formatar templates Edge usando o Prettier.

<div align="center">
  <sub>Feito com ❤︎ por <a href="https://github.com/JefteCosta">Jefte Costa</a> 
</div>

[npm-image]: https://img.shields.io/npm/v/@aarapucajs/prettier/latest.svg?style=for-the-badge&logo=npm
[npm-url]: https://www.npmjs.com/package/@arapucajs/prettier/v/latest 'npm'
[license-url]: LICENSE.md
[license-image]: https://img.shields.io/github/license/arapucajs/prettier?style=for-the

[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)