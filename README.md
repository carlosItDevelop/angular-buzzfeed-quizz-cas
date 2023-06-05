## Angular-BuzzFeed-Quizz - Originalmente criado por Felipe Aguiar | Update by Carlos A Santos

### Este projeto foi gerado (originalmente) pelo Angluar CLI na versão 14.1.2, mas foi atualizado para a versão 16.0.0, por Carlos A Santos.

<!-- ![Projeto Angular-BuzzFeed-Quizz](https://github.com/carlosItDevelop/angular-blog-desafio/blob/main/src/assets/capa.png "Projeto base - DIO | Digital Innovation One") -->

> Uma das alterações necessárias para a autalização do projeto é crias a pasta environment e seus respectivos arquivos de ambiente para Dev e Prod, que deixou de ser gerado automaticamente na versão 14.x do Angular, mas que a partir do Angular 15 criou-se a possibilidade de ser gerado pelo Angular CLI.

Pasta `environments` não é criada com o projeto a partir do `Angular 14`. Porém, com o `lançamento do Angular CLI 15.1`, um esquema de geração estará disponível para adicionar os arquivos de ambiente para todas as configurações de compilação existentes em um projeto. Exemplo de uso:

`ng generate environments`

Link de referência: [https://angular.io/guide/build#configure-environment-specific-defaults](https://cursos.alura.com.br/forum/topico-projeto-pasta-environments-nao-e-criada-com-o-projeto-a-partir-do-angular-14-268583)

1. [Atualize seu **`angular.json`** ou **`project.json`** para fazer substituições de arquivos onde os caminhos são da raiz do projeto até o arquivo de ambiente para substituir e com**1**](https://stackoverflow.com/questions/74558182/angular-15-cli-does-not-create-environments-folder-when-creating-an-angular-proj).

```typescript

"configurations": {
  "production": {
    ...
    "fileReplacements": [
        {
                  "replace": "./src/environments/environment.developement.ts",
                  "with": "./src/environments/environment.ts"
        }
    ],
  },
  "development": {
    ...
  }
},
"defaultConfiguration": "production"
}

```

---

- Obervação importante:

  - Para evitar a criação de arquivos de tests, podemos fazer de duas maneiras:

    - Usando o CLI: ng g c nome-do-component --skip-tests
    - Ou configurando para o projeto inteiro, conforme explicação abaixo:
    - Para evitar a criação de arquivos de teste ao gerar componentes, serviços ou diretivas globalmente no projeto, você pode alterar as configurações padrão no arquivo angular.json. Para fazer isso, localize a seção "schematics" e adicione ou modifique as opções de componentes, serviços e diretivas para incluir "skipTests": true. Por exemplo:

    ```typescript

    	{
    	  ...
    	  "projects": {
    		"meu-projeto": {
    		  ...
    		  "schematics": {
    			"@schematics/angular:component": {
    			  "skipTests": true},
    			"@schematics/angular:service": {
    			  "skipTests": true},
    			"@schematics/angular:directive": {
    			  "skipTests": true}
    		  },
    		  ...
    		}
    	  },
    	  ...
    	}
    ```

    - Ao aplicar essas configurações, o Angular CLI não gerará arquivos de teste quando você criar componentes, serviços ou diretivas no projeto.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
