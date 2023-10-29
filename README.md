# GifsApp

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 16.2.7.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

# Hosting the frontend project using Github Pages

## In VS Code

In order to upload your frontend project in Github Pages you must build the project,
that creates a `/dist/your-project-name` --> then you have to move `/your-project-name` to root directory --> rename it to `/docs`

That is the directory Github Pages will use to deploy your project.

## Scripting

If you want to, to make it easier the previous step you can download two npm packages called:

https://www.npmjs.com/package/del-cli

https://www.npmjs.com/package/copyfiles

And then in the package.json file add these 4 scripts:

    "build:href": "ng build --base-href ./",
    "build:github": "npm run delete:docs && npm run build:href && npm run copy:dist",
    "delete:docs": "del docs",
    "copy:dist": "copyfiles dist/gifs-app/* ./docs -f"

## In Github

Go to the Repository --> then Settings --> `Pages`

Deploy from a branch --> Main --> `/docs` --> Save

Go to Actions to find the `URL` of your site.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).
