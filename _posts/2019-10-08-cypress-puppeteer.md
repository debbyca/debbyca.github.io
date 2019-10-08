---
title: Calling Puppeteer from Cypress
category: Cypress, Puppeteer
---

As mentioned in a previous post, I used Cypress.io to run E2E testing. However, Cypress could not bypass Google's recaptcha.

<!-- more -->

Unwilling to let my tests go to waste, I managed to call Puppeteer from Cypress and present the test results in the same report.

The trick is to create cypress tasks and call puppeteer in a plugin file. I got how it can be done from [this GitHub thread](https://github.com/cypress-io/cypress/issues/2427).

While running the tests, I experienced a few timeout issues. To make the tests more stable, I specified a longer timeout value in `cypress.json`.

```
"taskTimeout": 5000000
```