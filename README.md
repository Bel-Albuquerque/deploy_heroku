# deploy_heroku

Abra o terminal e execute o seguinte comando:
```
curl https://cli-assets.heroku.com/install.sh | sh
```

E teste a instalação checando a versão do heroku:
```
heroku -v
```

Você deve ver algo como:
`heroku/7.60.2 linux-x64 node-v14.19.0`

Caso não veja a versão do heroku ou prefira instalar via snap faça o seguinte:
```
sudo snap install hello-world
```

O comando deverá responder da seguinte maneira:
`hello-world 6.4 from Canonical✓ installed`

Caso o comando retorne sucesso, siga para o próximo passo. Caso retorne que o comando snap não é conhecido, instale-o utilizando o apt:
```
apt-get update && apt-get install snapd
```

### Para sistemas Linux, instale o snap do Heroku CLI, executando o seguinte comando:
```
sudo snap install heroku --classic
```

Para sistemas macOS, instale o Heroku CLI, executando o seguinte comando:
```
brew tap heroku/brew && brew install heroku
```

### Logando no Heroku
⚠️ Atenção: é necessário autenticar o CLI para que os comandos funcionem corretamente.
Após a instalação ser concluída, você poderá acessar o Heroku por meio do seu terminal. Use o seguinte comando para logar com a sua conta:
```
heroku login
```
A seguir, o console solicitará que você pressione qualquer tecla para abrir o navegador e prosseguir com o login nele. Feito isso, será exibida no terminal a mensagem `done`

### Executando localmente
Para rodar um projeto localmente utilizando o CLI do Heroku, basta instalar as dependências do projeto e utilizar o CLI da seguinte maneira:
```
npm install # Instalando as dependências em um exemplo NodeJs utilizando o npm.
heroku local web
```

### Heroku remote
Para adicionar o remote do Heroku, basta usar o comando create do CLI dentro da pasta da aplicação, da seguinte maneira:
```
heroku create meu-deploy
```

Para remover o repositório:
```
git remote rm heroku
```
obs.: Como esse nome deve ser único, caso já exista algum repositório com este nome no Heroku, será retornado um erro solicitando que seja escolhido um novo. Por isso, um número aleatório no final pode evitar que esse erro ocorra. 😉

### Nomeação do remote
Por padrão, o CLI vai nomear todos os remotes criados como heroku. Porém, podemos criar o nosso remote passando um nome diferente. Isso pode ser feito utilizando a flag --remote:
```
heroku create meu-deploy-de-testes-29302 --remote heroku-homolog
```

### Renomeação do remote
Também podemos renomeá-los utilizando o comando git remote rename. Vale lembrar que o comando abaixo não vai manter o remote heroku, ele vai renomear o remote heroku para heroku-origin.
```
git remote rename heroku heroku-origin
```
obs.: Criar um outro remote da forma que fizemos ou renomear seu remote pode ser útil se você tiver múltiplos apps do Heroku usando o mesmo código fonte. Por exemplo, uma versão para o ambiente de testes e outra para um ambiente de produção. Nesse caso, cada app do Heroku tem seu próprio remote no seu repositório local.

https://app.betrybe.com/course/back-end/deployment/infraestrutura-deploy-com-heroku/30597149-145b-49a1-924c-bd8050a8f249/conteudo/b7d4a5c3-c013-4e3a-9573-d0434cd88359/preparando-um-projeto-para-deploy/84896476-2f76-4b22-8ff7-8cc842e6d9b8?use_case=next_button

