# Clitest

En esta sección aprenderemos principalmente sobre el AngularCLI

## Para generar automáticamente

Con el comando `ng g --help` podemos ver todo lo que angular pude generar.

```
Commands:
  ng g <schematic>              Run the provided schematic.  [default]
  ng g app-shell                Generates an application shell for running a server-side version of an app.
  ng g application [name]       Generates a new basic application definition in the "projects" subfolder of the workspace.  [aliases: app]
  ng g class [name]             Creates a new, generic class definition in the given project.  [aliases: cl]
  ng g component [name]         Creates a new, generic component definition in the given project.  [aliases: c]
  ng g config [type]            Generates a configuration file in the given project.
  ng g directive [name]         Creates a new, generic directive definition in the given project.  [aliases: d]
  ng g enum [name]              Generates a new, generic enum definition in the given project.  [aliases: e]
  ng g environments             Generates and configures environment files for a project.
  ng g guard [name]             Generates a new, generic route guard definition in the given project.  [aliases: g]
  ng g interceptor [name]       Creates a new, generic interceptor definition in the given project.
  ng g interface [name] [type]  Creates a new, generic interface definition in the given project.  [aliases: i]
  ng g library [name]           Creates a new, generic library project in the current workspace.  [aliases: lib]
  ng g module [name]            Creates a new, generic NgModule definition in the given project.  [aliases: m]
  ng g pipe [name]              Creates a new, generic pipe definition in the given project.  [aliases: p]
  ng g resolver [name]          Generates a new, generic resolver definition in the given project.  [aliases: r]
  ng g service [name]           Creates a new, generic service definition in the given project.  [aliases: s]
  ng g service-worker           Pass this schematic to the "run" command to create a service worker
  ng g web-worker [name]        Creates a new, generic web worker definition in the given project.

Arguments:
  schematic  The [collection:schematic] to run.  [string]

Options:
  --help         Shows a help message for this command in the console.  [boolean]
  --interactive  Enable interactive input prompts.  [boolean] [default: true]
  --dry-run      Run through and reports activity without writing out results.  [boolean] [default: false]
  --defaults     Disable interactive input prompts for options with a default.  [boolean] [default: false]
  --force        Force overwriting of existing files.  [boolean] [default: false]

```

## COMPONENT

Con el comando `ng g c --help` podemos ver un par de ayudas como:

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

Para generar un nuevo componente usamos en el CLI la siguiente expresion:

```
ng g c pages/about/about --flat --skip-tests
```

Esta expresion crea los siguientes archivos en la ruta indicada:

```
CREATE src/app/pages/about/about.component.html (20 bytes)
CREATE src/app/pages/about/about.component.ts (198 bytes)
CREATE src/app/pages/about/about.component.css (0 bytes)
UPDATE src/app/app.module.ts (478 bytes)
```

## SERVICE

Escribir `ng g s --help` y obtendremos las siguientes opcionces:

```
Options:
  --help         Shows a help message for this command in the console.  [boolean]
  --interactive  Enable interactive input prompts.  [boolean] [default: true]
  --dry-run      Run through and reports activity without writing out results.  [boolean] [default: false]
  --defaults     Disable interactive input prompts for options with a default.  [boolean] [default: false]
  --force        Force overwriting of existing files.  [boolean] [default: false]
  --flat         When true (the default), creates files at the top level of the project.  [boolean] [default: true]
  --project      The name of the project.  [string]
  --skip-tests   Do not create "spec.ts" test files for the new service.  [boolean] [default: false]

```

Para generear un nuevo servicio podemos escribir:

```
ng g s auth
```

Esto genera los siguientes archivos:

```
CREATE src/app/auth.service.spec.ts (347 bytes)
CREATE src/app/auth.service.ts (133 bytes)
```

El archivo de `.spec` son archivos de testign y se pueden borrar porque no afecta a la aplicacion.
Los `services` gracias a su decorador son de tipo global y no hay que importarlos ya que estan ligados al `root`.

```
@Injectable({
  providedIn: 'root'
})
```

Los archivos de `service` se pueden ubicar en cualquier otra carpeta, pero los path de los componenetes en los que se usa tienen que actualizarse.

#### Usar Service

Para hacer uso de los servicios solo hay que inyectarlos en el componente:

```
  constructor(
    private authService: AuthService,
  ) { }
```

## GUARD

Para generar un `guard` debemos escribir el siguiente comando:

```
ng g guard guard/auth --skip-tests

genera:
? Which type of guard would you like to create? CanActivate, CanLoad
CREATE src/app/guard/auth.guard.ts (651 bytes)
```

Los `guard` viene con diferentes opciones que se pueden seleccionar con la `[barra espaciadora]`.

## Para ubicar automáticamente los componetes/servicios/pipes/modulos y demás en las carpetas deseadas

## Aprenderemos a mover componentes y servicios mal generados a sus respectivos lugares

Simplemente tenemos que mover los componentes que queremos a sus nuevas carpetas y actualizar los path de los modulos para importarlos correctamente.
Si queremos borrar alguno de los archivos que se generaron, por algun motivos debemos fijarnos que su importacion o exportacion en el `component.ts` tambien sea actualizado.

## Además de un par de tips útiles que les pueden servir

Usar la bandera `--dry-run` nos permite simular la creacion de las carpetas para que podamos comprobar si es lo que necesitamos.

```
ng g s services/user --dry-run

genera:
CREATE src/app/services/user.service.spec.ts (347 bytes)
CREATE src/app/services/user.service.ts (133 bytes)

NOTE: The "--dry-run" option means no changes were made.

ng g s services/user -d --skip-tests

genera:
CREATE src/app/services/user.service.ts (133 bytes)

NOTE: The "--dry-run" option means no changes were made.
```

Ahora podemos quitar el `-d` y se generan los archivos que vimos.

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
