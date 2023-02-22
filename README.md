### About

- This is my research abount using chatGPT for write unit-tests in jest.
- Its guide how u can use this bot for write perfect tests.
- Chat GPT [Chat GPT site](https://chat.openai.com/chat "Click here..").

# Chat GPT for Unit-tests JS

![](https://www.atriainnovation.com/wp-content/uploads/2023/01/Portada-1080x675.jpg)

## Technologies used in the research:

- [![express][express.js]][express-url]
- [![npm][npm.com]][npm-url]
- [![jest][jest.com]][jest-url]

## Jest

The app use jest  `v. 29.4`

`$ npm install --save-dev jest`

## Setup
### package.json
```javascript
 "scripts": {
    "start": "node ./bin/www",
    "test": "jest"
  },
  ...
  "devDependencies": {
    "jest": "^29.4.3",  
  }
```
### Project Structure:
Automated tests are usually placed into the `__tests__` folder.
```console
    ├── ...
    ├── __tests__                       # tests folder
    │   ├── your_test.test.js           # Test FIle
    │   ├── your_test.test.js           # Test File
    │   ├── your_test.test.js           # Test File
    │   ├── your_test4.test.js          # Test File
    │   └── ...                         # etc.
    └── ...
```
### handebar-helpers.test.js example
```javascript
const { startTimeTransfer } = require("../utils/handebar-helpers");

...
// tested function
describe("startTimeTransfer function", () => {
    // test case 
  it("should return correct finish time for input '08:30'", () => {
    const result = startTimeTransfer("08:30");
    // function result === should be
    expect(result).toEqual("08:00 - 09:00");
  });
  // test case
  it("should return correct finish time for input '09:45'", () => {
    const result = startTimeTransfer("09:45");
    // function result === should be
    expect(result).toEqual("09:00 - 10:00");
  });
    // test case
  it("should return correct finish time for input '23:30'", () => {
    const result = startTimeTransfer("23:30");
    // function result === should be
    expect(result).toEqual("23:00 - 00:00");
  });
    // test case
  it("should return correct finish time for input '10:15'", () => {
    const result = startTimeTransfer("10:15");
    // function result === should be
    expect(result).toEqual("10:00 - 11:00");
  });
    // test case
  it("should return correct finish time for input '00:00'", () => {
    const result = startTimeTransfer("00:00");
    // function result === should be
    expect(result).toEqual("00:00 - 01:00");
  });
});
...
```
### Tests Run
Finally, `npm run test` and Jest will print this message:
```console
PASS  __tests__/handebar-helpers.test.js
```
### Errors
Your test can fail and jest will print this message:
```console
 FAIL  __tests__/handebar-helpers.test.js
  ● formatDateForPost function › should return a formatted date with hours                                     
    expect(received).toBe(expected) // Object.is equality    
    
    Expected: "23.02.2022-10:30"                                                                         
    Received: "23.02.2022-12:30"                          
```
## Chat GPT Usage
### Step 1
Write a function
```javascript
concatArray: function (array, type) {
    let result = [];
    if (type === 1) {
      result = array.map((i) => {
        return ` ${i.region}`;
      });
    }
    if (type === 2) {
      result = array.map((i) => {
        return ` ${i.company_name}`;
      });
    }

    return result.toString();
  },
```
### Step 2
Copy function to chat GPT input and say: `write me some tests for this function in jest` then pase your function below 

> write me some tests for this function in jest:
```javascript
concatArray: function (array, type) {
    let result = [];
    if (type === 1) {
      result = array.map((i) => {
        return ` ${i.region}`;
      });
    }
    if (type === 2) {
      result = array.map((i) => {
        return ` ${i.company_name}`;
      });
    }

    return result.toString();
  }
```
### Step 3
Chat GPT answer:

> Sure! Here are some tests for the concatArray function using Jest:
```javascript
describe('concatArray', () => {
  const array = [
    { region: 'Asia', company_name: 'ABC Corp' },
    { region: 'Europe', company_name: 'XYZ Inc' },
    { region: 'North America', company_name: 'Acme Corp' },
  ];

  it('should concatenate array by region when type is 1', () => {
    const type = 1;
    const expected = ' Asia, Europe, North America';
    const result = concatArray(array, type);
    expect(result).toEqual(expected);
  });

  it('should concatenate array by company name when type is 2', () => {
    const type = 2;
    const expected = ' ABC Corp, XYZ Inc, Acme Corp';
    const result = concatArray(array, type);
    expect(result).toEqual(expected);
  });
});
```
> Then you need to copy this function and paste this to your `*.test.js file` , import your functon `const {concatArray} = require('../path_to_function')` and **enjoy**.

## Anomaly
### Generating stop
> **Q: Sometimes chat GPT can stop typing without any errors, it can be if your function is to long or it includes ua/rus words**
>
> **A:** Try to **regenerate** the answer or ask chat GPT `write some test cases without code`, then write tests **one by one**.

### Incorrect answer
> **Q: Sometimes chat GPT may misunderstand you, and give you wrong test cases**
>
> **A:** Try to **regenerate** the answer or give more details like a `use mock for this function`.

### To may requests
> **Q: To many requests in 1 hour. Try later.**
>
> **A:** **Wait**...

## Acknowledgments
Resources that helped me in development.

* [Chat GPT](https://chat.openai.com/chat)
* [Jest](https://jestjs.io/docs/getting-started)
* [SuperTest](https://www.npmjs.com/package/supertest)
* [YouTube](https://www.youtube.com/watch?v=r5L1XRZaCR0&t=654s)

## My Links
- [![linkedin][linkedin.com]][linkedin-url]
- [![telegram][telegram.com]][telegram-url]
- [![portfolio][portfolio.com]][portfolio-url]
<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[express.js]: https://img.shields.io/badge/Express-20232A?style=for-the-badge&logo=express&logoColor=white
[express-url]: https://expressjs.com/
[jest.com]: https://img.shields.io/badge/Jest-20232A?style=for-the-badge&logo=jest&logoColor=green
[jest-url]: https://jestjs.io/
[npm.com]: https://img.shields.io/badge/NPM-20232A?style=for-the-badge&logo=npm&logoColor=764abc
[npm-url]: https://www.npmjs.com/
[linkedin.com]: https://img.shields.io/badge/LinkedIn-20232A?style=for-the-badge&logo=linkedin&logoColor=wgute
[linkedin-url]: https://www.linkedin.com/in/dmitry-morozov-082288228/
[telegram.com]: https://img.shields.io/badge/Telegram-20232A?style=for-the-badge&logo=telegram&logoColor=white
[telegram-url]: https://t.me/r3ason_why
[portfolio.com]: https://img.shields.io/badge/Portfolio-20232A?style=for-the-badge&logo=github&logoColor=white
[portfolio-url]: https://s1een.github.io/my_cv_site/

