# HiRez.io Testing Snippets

VS Code snippets that will make your testing life easier.

[![Version](https://vsmarketplacebadge.apphb.com/version/hirez.hirez-testing-snippets.svg)](https://marketplace.visualstudio.com/items?itemName=hirez.hirez-testing-snippets)
[![Installs](https://vsmarketplacebadge.apphb.com/installs-short/hirez.hirez-testing-snippets.svg)](https://marketplace.visualstudio.com/items?itemName=hirez.hirez-testing-snippets)
[![Code of Conduct](https://img.shields.io/badge/code%20of-conduct-ff69b4.svg?style=flat-square)](CODE_OF_CONDUCT.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

## Want to learn more about how to use these snippets correctly?

<div align="center">
  <a href="http://testangular.com/?utm_source=github&utm_medium=link&utm_campaign=vscode-testing-snippets">
    <img src="https://github.com/hirezio/vscode-testing-snippets/raw/master/assets/test-angular.jpg"
      alt="TestAngular.com - Free Angular Testing Workshop - The Roadmap to Angular Testing Mastery"
      width="600"
    />
  </a>
</div>

<br/>

# Available Snippets:

| Snippet | Description |
| ------- | ----------|
| `desc` | Generates an a `describe` function |
| `giv` | Generates an a `Given` function |
| `when` | Generates an a `When` function |
| `then` | Generates an a `Then` function |
| `testcase` | `describe` with `Given` and `Then` |
| `descwhen` | `describe` with `When` |
| `acomptest` | Generates an Angular Component test |
| `aservtest` | Generates an Angular Service test |
| `ngtestbase` | Generates a base for an Angular micro test |
| `addSpy` | Adds a jasmine/jest auto spy boilerplate code |
| `addDep` | shortest way to add a private typed dependency to a class constructor |
| `methodplaceholder` | Generates an empty method that throws an "unimplemented" error |

<br/>

## Snippets Usage

### SNIPPET: `desc`

*Output:*
```js
describe('<Your Description>', () => {
  
});
```
---

### SNIPPET: `giv`

*Output:*
```js
Given(() => {
  
});
```
---

### SNIPPET: `when`
*Output:*
```js
When(() => {
  
});
```

---

### SNIPPET: `then`
*Output:*
```js
Then(() => {
  
});
```

---


### SNIPPET: `testcase`
*Output:*
```js
describe('GIVEN: <--Your Given Description-->', () => {
  
  Given(() => {
  
  });
  
  Then('<Your THEN description>', () => {
  
  });
});
```

---

### SNIPPET: `descwhen`
*Output:*
```js
describe('METHOD: <Method Name>', () => {
  
  When(() => {
    serviceUnderTest.<Method Name>()
  });
  
});
```

---

### SNIPPET: `acomptest`

⚠ INSTRUCTIONS: 
1. Choose between "jasmine" or "jest"
2. Hit "tab" to jump between variables


*Output:*
```ts
import { TestBed } from '@angular/core/testing';
import { Spy, createSpyFromClass } from '<--Your Testing Framework-->-auto-spies';

describe('<--Your Component Type-->', () => {
  let componentUnderTest: <--Your Component Type-->;

  Given(() => {
    TestBed.configureTestingModule({
      providers: [<--Your Component Type-->]
    });

    componentUnderTest = TestBed.inject(<--Your Component Type-->);

  });

  describe('METHOD: <--Method Name-->', () => {

    When(() => {
      componentUnderTest.<--Method Name-->();
    });

    describe('GIVEN <--Your Given Description-->', () => {
      Given(() => {
        // <--Your Given Description-->
        
      });
      Then('<--Your Then Description-->', () => {
        // <--Your Then Description-->
      });
    });

  });
});

```

---

### SNIPPET: `aservtest`

⚠ INSTRUCTIONS: 
1. Choose between "jasmine" or "jest"
2. Hit "tab" to jump between variables

*Output:*
```ts
import { TestBed } from '@angular/core/testing';
import { Spy, createSpyFromClass } from '<--Your Testing Framework-->-auto-spies';

describe('<--Your Service Type-->', () => {
  let serviceUnderTest: <--Your Service Type-->;

  let actualResult: any;

  Given(() => {
    TestBed.configureTestingModule({
      providers: [<--Your Service Type-->]
    });

    serviceUnderTest = TestBed.inject(<--Your Service Type-->);

    actualResult = undefined;

  });

  describe('METHOD: <--Method Name-->', () => {

    When(() => {
      serviceUnderTest.<--Method Name-->();
    });

    describe('GIVEN <--Your Given Description-->', () => {
      Given(() => {
        // <--Your Given Description-->
        
      });
      Then('<--Your Then Description-->', () => {
        // <--Your Then Description-->
      });
    });

  });
});

```

---

### SNIPPET: `ngtestbase`

⚠ INSTRUCTIONS: 
1. Choose between "jasmine" or "jest"
2. Hit "tab" to jump between variables
3. Choose between "component", "service", "directive" or "pipe"

*Output:*
```ts
import { TestBed } from '@angular/core/testing';
import { Spy, createSpyFromClass } from '<--Your Testing Framework-->-auto-spies';

describe('<--Type To Test-->', () => {
  let <--Angular Type Choice-->UnderTest: <--Type To Test-->;

  let actualResult: any;

  Given(() => {
    TestBed.configureTestingModule({
      providers: [<--Type To Test-->]
    });

    <--Angular Type Choice-->UnderTest = TestBed.inject(<--Type To Test-->);

    actualResult = undefined;

  });

  describe('METHOD: <--Method Name-->', () => {

  });
});

```

---

### SNIPPET: `addSpy`

Makes adding an "auto spy" very easy. 


⚠ INSTRUCTIONS: 
1. Write / paste your class type
2. Hit "tab" to turn the variable to camelCase ("lowercase"s the first letter)
3. Cut and paste each line to its appropriate place

*Output:*
```js
// This goes in your first "Describe":
let myServiceTypeSpy: Spy<MyServiceType>;

// This goes in your TestBed's "providers" array:
{ provide: MyServiceType, useValue: createSpyFromClass(MyServiceType) },

// This goes in your first Given:
MyServiceTypeSpy = TestBed.inject<any>(MyServiceType);
```

---

### SNIPPET: `addDep`

Makes adding a class constructor dependency very easy. 

⚠ INSTRUCTIONS: 
1. Write or paste your class type
2. Hit "tab" to turn the variable to camelCase ("lowercase"s the first letter)

*Output:*
```js
private myServiceType: MyServiceType,
```

---

### SNIPPET: `methodplaceholder`
*Output:*
```js
<--myMethod-->() {
  throw new Error('Method not implemented.');
}
```



<br/>

## Contributing

Want to contribute? Yayy! 🎉

Please read and follow our [Contributing Guidelines](CONTRIBUTING.md) to learn what are the right steps to take before contributing your time, effort and code.

Thanks 🙏

<br/>

## Code Of Conduct

Be kind to each other and please read our [code of conduct](CODE_OF_CONDUCT.md).

<br/>

## License

MIT
