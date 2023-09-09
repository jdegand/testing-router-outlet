# Testing Router Outlet

[Angular Challenges](https://github.com/tomalaforge/angular-challenges) #17 Router Testing

## Built With

- [Angular](https://angular.io)
- [Angular CLI](https://github.com/angular/angular-cli) version 16.2.0.
- [Testing Library Angular](https://testing-library.com/docs/angular-testing-library/intro)
- [Jest](https://jestjs.io)
- [Cypress](https://www.cypress.io)

## Thoughts

- Cypress 13 is a mess right now (Sept 2023).
- I think the lazy loading of the search component causes the button to not appear as disabled and prevents the error class from being in the dom on the initial load.  Testing-library sees fallback html without either thing being set.  
- Thus, you need to do something to get the component to re-render.  
- screen.debug() is extremely useful.  
- When running the app, you don't have to click the link to show the form like you have to do in cypress. 
- There is a weird disconnect between actions necessary for tests but not when you run the app.  
- I was tempted to add selectors to the html at points.  The selectors I used are mostly generic and a developer possibly would have to change them if the app were to be reworked.  
- When using jest with angular, there are issues with using modules.  You have to use a different jest.config and add other properties to the tsconfig.spec.json.  Even with all the extra boilerplate, I've had problems getting a configuration that works reliably.  I think module testing errors could be library-specific.  
- With jest tests, you get a warning error - Error: Not implemented: navigation (except hash changes).  Need to investigate more.
- It may have been better to vary test queries more but I think the challenge has a compare and contrast element to it.  (Testing-Library vs Cypress) 

## How to Use

```bash 

git clone https://github.com/jdegand/testing-router-outlet.git

# cd into the directory
npm install

# Jest 

npm test

# Jest with Coverage

npm run test:coverage

# Cypress

npm run cypress:open
```

## Useful Resources

- [Blog](https://timdeschryver.dev/blog/getting-the-most-value-out-of-your-angular-component-tests) - this seems to be the inspiration for this challenge
- [CodeCraft](https://codecraft.tv/courses/angular/unit-testing/routing/) - routing testing old way
- [Github](https://github.com/testing-library/jest-dom/discussions/325) - jest dom toBeDisabled()
- [Jest Preset Angular](https://thymikee.github.io/jest-preset-angular/docs/guides/angular-13+)- problems from modules
- [Stack Overflow](https://stackoverflow.com/questions/67645895/cannot-find-module-students-json-consider-using-resolvejsonmodule-to-im) - cannot find module
- [Github](https://github.com/testing-library/react-testing-library/issues/716) - Previous render sometimes leaking into next test
- [Stack Overflow](https://stackoverflow.com/questions/62473970/best-way-to-test-input-value-in-dom-testing-library-or-react-testing-library) - best way to test input value in dom testing library or react testing library
- [Stack Overflow](https://stackoverflow.com/questions/54090231/how-to-fix-error-not-implemented-navigation-except-hash-changes) - how to fix error not implemented navigation except hash changes
- [Cypress Docs](https://docs.cypress.io/guides/component-testing/angular/examples) - angular examples
- [Github](https://github.com/cypress-io/cypress-component-testing-apps/blob/main/angular-standalone/src/app/app.component.cy.ts) - angular standalone app.component.cy.ts
- [Stack Exchange](https://sqa.stackexchange.com/questions/34319/how-to-check-a-button-is-disabled-using-cypress) - check a button is disabled in Cypress
- [BrowserStack](https://www.browserstack.com/guide/cypress-test-if-element-exists) - cypress test if element exists
