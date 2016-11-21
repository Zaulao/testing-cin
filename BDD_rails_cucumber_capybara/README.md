# BDD - IF1009

Preparação do ambiente Rails, cucumber e capybara utilizando Vagrant

### Pré-requesitos

Instalar o VirtualBox - https://www.virtualbox.org/wiki/Downloads

Instalar o Vagrant - https://www.vagrantup.com/downloads.html

Instalar o plugin para convidado do VirtuaBox para o Vagrant, que permite a divisão de dados entre host e VM

```
vagrant plugin install vagrant-vbguest
```

### Instalando

[Marcelo: nao entendi.  esta pasta jah existe no repo!]
Fazer download a pasta BDD_rails_cucumber_capybara  

Criar um diretório "seu_projeto_teste"

[Marcelo: por que vc. jah nao este diretorio com o arquivo dentro?]
Colocar Vagrantefile da pasta BDD_rails_cucumber_capybara no "seu_projeto_teste" e dentro do diretório seu_projeto_teste:
	
```
vagrant up
```
OBS: Nas ultimas 7 linhas de saída do comando haverá a informação do endereço e da porta, que por padrão é 127.0.0.1 e 2222 respectivamente. 

## Conectando ao servidor

Para acessar a máquina virtual pelo Linux e Mac usar o comando:
```
vagrant ssh
```
Em caso de estar usando o Windows é necessário baixar o PuTTy e seguir os seguintes passos:
```
Abra o PuTTy

Preencha Host Name (or IP adress) com "vagrant@ip_da_saida_vagrant_up" (default 127.0.0.1)

Preencha Port com "porta_da_saida_vagrant_up" (default 2222)

Selecionar SSH->Selecionar Auth->Private key file for authentication->BDD_rails_cucumber_capybara->Selecione vagrant.ppk->Open  
```

### Configurando o Rails

Após isso, no console do PUTTy, ou do Linux/Mac você estará dentro da VM (/vagrant):

Utilizar comando:
```
gem install rails
```

Copiar para dentro do diretório "seu_projeto_teste" a pasta bdd_teste_app, que contém o ambiente para testes

Use o comando:
```
ls 
```
para visualizar o diretorio do app.

Use o comando:
```
cd bdd_teste_app 
```
para entrar no diretório da aplicação (/vagrant/bdd_teste_app).

Utiizar comando:
```
bundle install
```
Para instalar as gems necessárias.

Siga as instruções em Tutorial_Cucumber_Capybara.txt para rodar os testes bdd

Para observar o servidor rodando utilize, dentro do diretorio bdd_teste_app, o comando:
```
rails server -b 0.0.0.0 
```
Utilize o bronser e o endereço 127.0.0.1:3000 para visualizar a aplicação em contrução usada no exemplo.

