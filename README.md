# SecondApp

## What is this about

A tic-tac-toe game build with Angular.

**Components Structure:** `AppComponent` ▶ `BoardComponent` ▶ `SquareComponent`

> What's in BoardComponent?

Variables:

1. We need 9 squares, so, an array `squares: any[]` is declared.
2. 2 user will click the squares alternatively, so, to define who is next to click a boolean variable `xIsNext: boolean` is declared.
3. To define who wins, a string variable `winner: string` is declared.
4. To disable the buttons after getting any result, a boolean variable `isDisabled: boolean` is declared.

```ts
squares: any[];
xIsNext: boolean;
winner: string;
isDisabled: boolean;
```

Methods/Functions:

1. `ngInit()`, this is initialized when this component loads everytime. This is a lifecycle method for this component.
   ```ts
   ngOnInit(): void {
       this.newGame();
   }
   ```
2. `newGame()` is called from the above method. The `square` array will be filled with 9 null values.
   ```ts
   newGame(): void {
       this.squares = Array(9).fill(null);
       this.xIsNext = true;
       this.winner = null;
       this.isDisabled = false;
   }
   ```
3. `get player()` function to show whose turn it is.

   ```ts
   get player() {
       return this.xIsNext ? 'X' : 'O';
   }
   ```

why `get player()`? why not only `player()`? Because I want the value that the function will return. That's why `get` keyword is used before the function name. By using this we can add the function name in the template file.

    ```html
    <h2>{{ player }}</h2>
    ```

---

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 10.2.0.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.
