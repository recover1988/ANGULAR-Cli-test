# Clitest

En esta sección aprenderemos principalmente sobre el AngularCLI

## Para generar automáticamente componentes

Con el comando `ng g c --help` podemos ver un par de ayudas como

```
Options:
  --help             Shows a help message for this command in the console.  [boolean]

  --interactive      Enable interactive input prompts.  [boolean] [default: true]

  --dry-run          Run through and reports activity without writing out results.  [boolean]
   [default: false]
  --defaults         Disable interactive input prompts for options with a default.  [boolean]
   [default: false]
  --force            Force overwriting of existing files.  [boolean] [default: false]

  -c, --change-detection    The change detection strategy to use in the new component.  [string] [choices: "Default", "OnPush"] [default: "Default"]
  -b, --display-block       Specifies if the style will contain `:host { display: block; }`.  [boolean] [default: false]
  --export           The declaring NgModule exports this component.  [boolean] [default: false]
  --flat             Create the new files at the top level of the current project.  [boolean] [default: false]
  -s, --inline-style        Include styles inline in the component.ts file. Only CSS styles can be included inline. By default, an external styles file is created and referenced in the component.ts file.  [boolean] [default: false]
  -t, --inline-template     Include template inline in the component.ts file. By default, an external template file is created and referenced in the component.ts file.  [boolean] [default: false]
  -m, --module       The declaring NgModule.  [string]
  -p, --prefix       The prefix to apply to the generated component selector.  [string]
  --project          The name of the project.  [string]
  --selector         The HTML selector to use for this component.  [string]
  --skip-import      Do not import this component into the owning NgModule.  [boolean] [default: false]
  --skip-selector    Specifies if the component should have a selector or not.  [boolean] [default: false]
  --skip-tests       Do not create "spec.ts" test files for the new component.  [boolean] [default: false]
  --standalone       Whether the generated component is standalone.  [boolean] [default: false]
  --style            The file extension or preprocessor to use for style files, or 'none' to skip generating the style file.  [string] [choices: "css", "scss", "sass", "less", "none"] [default: "css"]
  --type             Adds a developer-defined type to the filename, in the format "name.type.ts".  [string] [default: "Component"]
  -v, --view-encapsulation  The view encapsulation strategy to use in the new component.  [string] [choices: "Emulated", "None", "ShadowDom"]

```

## Para ubicar automáticamente los componetes/servicios/pipes/modulos y demás en las carpetas deseadas

## Aprenderemos a mover componentes y servicios mal generados a sus respectivos lugares

## Además de un par de tips útiles que les pueden servir

El objetivo principal, es ayudarles a que dominemos este generador automático, porque próximamente lo usaremos mucho para crear bastantes componentes, servicios y necesito que sepamos manejarlo bien y con confianza.

Al finalizar la sección, hay una tarea de reforzamiento.

# Angular

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 15.2.1.

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
