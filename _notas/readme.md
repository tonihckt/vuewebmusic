#### crear proyecto vue-webpack
$ npm install -g @vue/cli
<!-- $ npm install -g @vue/cli-init -->
$ npm install -g @vue/cli-service-global
<!-- $ vue init webpack-simple my-project -->
$ vue create vuecli-project
<!-- $ vue init bootstrap-vue/webpack-simple getting-started -->
$ cd my-project
$ npm install
$ npm run dev
##### -------------------------------
https://unpkg.com/bootstrap@4.1.3/dist/css/bootstrap.min.css
https://unpkg.com/bootstrap-vue@2.0.0/dist/bootstrap-vue.css
https://unpkg.com/vue@2.6.10/dist/vue.min.js
https://unpkg.com/bootstrap-vue@2.0.0/dist/bootstrap-vue.min.js
https://unpkg.com/babel-polyfill@6.26.0/dist/polyfill.min.js


# o que te descargues la ultima version
<!-- Add Bootstrap and Bootstrap-Vue CSS to the <head> section -->
<link type="text/css" rel="stylesheet" href="https://unpkg.com/bootstrap/dist/css/bootstrap.min.css"/>
<link type="text/css" rel="stylesheet" href="https://unpkg.com/bootstrap-vue@latest/dist/bootstrap-vue.min.css"/>

<!-- Add Vue and Bootstrap-Vue JS just before the closing </body> tag -->
<script src="https://unpkg.com/vue/dist/vue.min.js"></script>
<script src="https://unpkg.com/bootstrap-vue@latest/dist/bootstrap-vue.min.js"></script>
Si por alguna razón necesita admitir navegadores heredados, también puede incluir @ babel / polyfill , que emulará un entorno ES2015 + completo:
<script src="https://unpkg.com/babel-polyfill@latest/dist/polyfill.min.js"></script>

