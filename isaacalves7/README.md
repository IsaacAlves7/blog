# IsaacAlves7 - Blog & Portfolio 

## 0. Guia de instalação do projeto
```sh
rails new isaacalves7 -d postgresql
```

```sh
bundle install
```

## 1. Instale o Webpacker
```ruby
gem 'webpacker', '~> 5.4', '>= 5.4.3'
```

```sh
rails webpacker:install
```

### `/config/webpack/environment.js`

```javascript
const { environment}= require('@rails/webpacker');

const webpack = require( 'webpack');
    environment.plugins.append(
      'Provide',
    new webpack.ProvidePlugin({
        $: 'jquery/src/jquery',
        jQuery: 'jquery/sc/jquery',
        Popper: ['popper.js', 'default']
    })
);

module.exports = environment;
```

## 2. Instale o Bootstrap, jQuery e Popper.js
```sh
yarn add bootstrap jquery popper.js
```

## 3. Importe o Bootstrap em `/app/javascript/application.js`
```javascript
// Configure your import map in config/importmap.rb. Read more: https://github.com/rails/importmap-rails
import "@hotwired/turbo-rails"
import "controllers"
import "bootstrap"
```

## 4. Renomeie o `/assets/stylesheets/application.css` para a extensão `.scss`

E dentro desse arquivo:
```scss
@import "bootstrap/scss/bootstrap"; 
@import "./actiontext.scss";
```

## 5. Instalar o Action_Text

```ruby
gem 'image_processing', '~> 1.12', '>= 1.12.2'
```

```sh
rails action_text:install
```

## 6. Criando o banco de dados e as tabelas

```sh
rails db:create db:migrate
```

## 7. No `/assets/stylesheets/actiontext.scss`:

```scss
@import "trix/dist/trix";
```

## 8. Execute o seguinte código no seu terminal

```sh
rails g controller home index
```