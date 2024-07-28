# CRIAÇÃO PROJETO NATIVE [ Ambiente LINUX ]

## Comando para criar o projeto

```
npx react-native init NomeDoSeuProjeto
```

## Dentro do projeto, deve-se criar o arquivo local.properties dentro do diretório android

Inserir a instrução abaixo:

```
sdk.dir=/home/jorge/Android/Sdk
```

## Comandos para reconfigurar o novo ambiente

```
cd android
./gradlew clean
cd ..
npm install
```

### Comando para iniciar no cell

npm start
opc a

---

# Configurar ambiente JDK e permissões

<a href="https://www.oracle.com/br/java/technologies/downloads/#java17" target="_blank">Link para instalação do JDK</a>

## Criação das variáveis de ambiente

Criar o arquivo abaixo:

```
~/.zshrc
```

Inserir dentro dele as instruções abaixo:

```
export ANDROID_HOME=$HOME/Android/Sdk
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

Criar no final do arquivo '~/.bashrc' a instrução abaixo:

```
export JAVA_HOME=/usr/lib/jvm/jdk-17.0.12-oracle-x64
export PATH=/usr/lib/jvm/jdk-17.0.12-oracle-x64/bin/:$PATH
```

Criar/adc arquivo '~/.bash_profile'

```
export ANDROID_HOME=~/Android/Sdk
export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools
export PATH=/usr/lib/jvm/jdk-17.0.12-oracle-x64/bin/:$PATH
```

# Configuração do celular

Precisamos listar a usb do cell, comando utilizado:

```
lsusb
```

Usar os primeiros 4 números após ID 'XXXX'

Usar o comando abaixo para adcionar as regras

```
echo 'SUBSYSTEM=="usb", ATTR{idVendor}=="XXXX", MODE="0666", GROUP="plugdev"' | sudo tee /etc/udev/rules.d/51-android-usb.rules
```

## verificando se o cell é reconhecido

comando:

```
adb devices
```

Após isto basta executar novamente a aplicação com o celular conectado ao computador.

### Configuração Eslint e Prettier

Referência <a href="https://github.com/devfraga/react-native-eslint-prettier">aqui </a>
