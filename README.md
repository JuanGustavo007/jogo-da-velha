# jogo-da-velha

Jogo da velha usando os conceitos básicos do vue.

## Lógica usada

A forma como eu pensei foi a seguinte: - Uso de if em cada posição do tabuleiro e o "and" dentro desses ifs, ou seja, quando as condições fossem satisfeitas ele criava o alert de quem ganhou o jogo. O usuário não pode digitar nada diferente de "x" ou "o", para isso eu coloquei um limite de teclas no input e também a restrição de qual tecla.
Para mostrar quem ganhou, eu usei o watch do vue que fica observando o v-model com o input, e também como ja citado, o uso de condições (v-if para mostrar o alert e os ifs do javascript para mostrar quem ganhou).

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
