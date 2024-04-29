# Configuração do Backstage

Backstage é uma plataforma de código aberto para construir portais para desenvolvedores. Alimentado por um catálogo de software centralizado, Backstage restaura a ordem em seus microsserviços e infraestrutura e permite que suas equipes de produto entreguem código de alta qualidade rapidamente — sem comprometer a autonomia.

Backstage unifica todas as suas ferramentas de infraestrutura, serviços e documentação para criar um ambiente de desenvolvimento simplificado de ponta a ponta.

## Passo a Passo

### Criação da Aplicação Backstage


1. **Inicialização do Projeto:**
    No terminal, execute o comando abaixo para iniciar a criação do projeto:
    ```npx @backstage/create-app@latest --skip-install```
    Este comando cria a estrutura básica do projeto sem instalar as dependências, permitindo uma configuração manual posterior.

2. **Definição do Nome do Projeto:**
Dei um nome para a minha aplicação: `ponderadacarol`.

![382120ae-a25d-4c35-bf7b-b94cdd072836](https://github.com/CFFricks/ponderadacarol/assets/99102201/c45e9c25-540c-4024-9fd7-856a6a9d1dcb)

3. **Navegação até o Diretório do Projeto:**
Utilizei o comando abaixo para entrar no diretório do projeto criado:
    ```cd ponderadacarol```
![image](https://github.com/CFFricks/ponderadacarol/assets/99102201/4d0eb1b0-a1b5-4b48-b4bd-05e306efe00f)

4. **Instalação das Dependências:**
Executei o seguinte comando para instalar as dependências necessárias:
```yarn install```

(É necessario tem um node maior que a versão 18.12)

</br>

  ![image](https://github.com/CFFricks/ponderadacarol/assets/99102201/0fec34d0-23c3-4e65-8032-d420de6feb92)
<br>
</br>

  ![image](https://github.com/CFFricks/ponderadacarol/assets/99102201/dcb5092a-f8d1-4a9a-acad-4c6f48c326b7)

### Compilação do Projeto

1. **Travamento das Dependências:**
Por meio do comando é garantido a consistência das versões das dependências:
```yarn install --frozen-lockfile```

![image](https://github.com/CFFricks/ponderadacarol/assets/99102201/e2742e2a-4b71-4c89-889d-a8a1a2b92d40)

3. **Compilação de Types:**
Compilei os types necessários para o projeto com:
```yarn tsc```
</br>

![image](https://github.com/CFFricks/ponderadacarol/assets/99102201/1b8a054e-94bb-4f9a-87d6-870273390d84)

5. **Build Completo:**
Construi o backend do projeto com:
```yarn build:backend```
</br>

![image](https://github.com/CFFricks/ponderadacarol/assets/99102201/7ba8f3b7-9dbf-4020-9327-2861ef6fcadb)
</br>

![image](https://github.com/CFFricks/ponderadacarol/assets/99102201/35a73d8c-11fb-413a-b573-a10a7e07546b)

### Dockerização do Projeto

1. **Ajustes no Dockerfile:**
Abri o projeto em no VS Code e localizei o `Dockerfile` no caminho `packages/backend/Dockerfile`. Substitui o conteúdo por uma configuração fornecida pelo Felipe Saadi, no canal do Slack.

2. **Construção da Imagem Docker:**
No terminal, construi a imagem Docker sem usar caches de compilações anteriores por meio do comando:
```docker image build . -f packages/backend/Dockerfile --tag backstage --no-cache```

![image](https://github.com/CFFricks/ponderadacarol/assets/99102201/06c3f1e9-f00b-4582-bfc5-d5aabb47efca)

3. **Execução do Container:**
Execução do container Docker que hospeda o Backstage:
```docker run -it -p 7007:7007 backstage```
![image](https://github.com/CFFricks/ponderadacarol/assets/99102201/1ac68574-70c0-4fc9-9710-edc0a795e062)


4. **Verificação:**
Por ultimo acessamos o Backstage por meio do link: `http://localhost:7007` no navegador.
![image](https://github.com/CFFricks/ponderadacarol/assets/99102201/6e839875-7faa-41c7-aa97-8a2b9b344d58)

