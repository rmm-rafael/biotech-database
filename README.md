# biotech-database
biotech-database

# tools
- Para gerenciamento de versão do node nvm (https://www.freecodecamp.org/news/nvm-for-windows-how-to-download-and-install-node-version-manager-in-windows-10/)
- Para compilar projeto (https://classic.yarnpkg.com/lang/en/docs/install/#debian-stable)

# pré-requisitos
 - node v12.22.7
 - yarn 1.22.17
 - @vue/cli 4.5.15


# 1 Instalar ferramentas

## 1.1 Atribuir a versão do node

```
nvm use v12.22.7
```

### Verificar versão do node
```
nvm ls
```

Dados de saída do comando:

```
~/dev/workspace 
╰─ nvm ls
       v10.19.0
->     v12.22.7
      v12.22.12
```

## 1.2 Instalar yarn

```
npm install --global yarn
```

### Verificar versão do yarn
```
yarn --version
```

Dados de saída do comando:

```
~/dev/workspace 
╰─ yarn --version
1.22.17

```

## 1.3 Instalar vue-cli

```
yarn global add @vue/cli
```

### Verificar versão do vue
```
vue --version
```

Dados de saída do comando:

```
~/dev/workspace 
╰─ vue --version
@vue/cli 4.5.15
```


# 2 Rodar o projeto Local

# 2.1 Baixando as dependencias do projeto

```
yarn
```

# 2.1 Rodando local

```
yarn serve
```
