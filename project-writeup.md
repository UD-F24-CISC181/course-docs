---
title: Final Project Writeup
layout: page
---

# Final Project Writeup

Welcome to the Final Project!

You are going to create a Loan Amortization Calculator! This calculator will allow users to input details of a loan (such as amount, interest rate, and loan term), and then see a table of how the loan is paid off over time. This is a common tool used by banks and financial institutions to help people understand how loans work.

Most consumer loans use compound interest.  The breakdown of payment (principle and interest) isn't the same over time- the lender pays most of the interest component up front.

For example, a loan of $300,000 at 7% for 30 years has a fixed payment of $1995.91. For the first payment, $249.91 is applied to principal and $1750.00 is paid in interest. In the 15th payment, $266.77 is principal and $1729.14 is interest.

One strategy to beat the math is to pay extra on principle.  If you paid an extra $100 in the example above, 50 payments would be saved and a total of $69,337.93 would be saved in interest payments!

# Work Schedule

The final project will be released in phases, with each phase building on the previous one. The phases so far are:

1. **Phase 0**: Starting Code
2. **Phase 1**: Basic Calculations
3. **Phase 2**: Loan Calculator UI

More details about each phase are provided below.

## Phase 0: Starting Code

To begin the project, follow this link to clone the assignment: <https://classroom.github.com/a/o4X-3ayf>

The starting point to browse the repository is the `src` folder, which has two main directories: the `code/` (containing the math and logic for the loan calculator) and the `app/` (which will eventually contain the web interface for the loan calculator). We will start in the `code/` directory. Once you've installed the dependencies, we recommend running the tests as you work:

```bash
npm install
npm run test
```

The initial project repository has financial formulas for the following common calculations:

* `calculatePMT` – Calculate payment based on Present Value (`presentValue`), Future Value (`futureValue`), Number of Payments (`totalPeriods`) and interest rate (`periodicInterestRate`).
* `calculateIPMT` – Determine the interest paid for a given payment (with the same parameters) with no extra payments.
* `calculatePPMT` – Determine the principle paid for a given payment (with the same parameters) with no extra payments.

The code for these calculations are already provided to you in a static `Finance` class, along with the incomplete versions of the `Payment` and `Loan` classes.

The `Loan` class provides the following already-implemented methods:

* `roundTo` - A helper function for rounding numbers to a specified number of decimal places.
* `getPMT` – Returns the already-computed monthly payment for the loan.
* `getPayments` – Returns an array of `Payment` objects representing the payments for the loan.

## Phase 1: Basic Calculations

The `Loan` class has the core logic of your application. You will need to finish implementing the following methods:

- [ ] The constructor, which should use the `Finance.calculatePMT` function to set the `pmt` field.
- [ ] The `totalExpectedInterest` method, which should return the total interest paid over the life of the loan.
- [ ] The `totalExpectedPayments` method, which should return the total amount paid over the life of the loan.
- [ ] The `totalPaidInterest` method, which should return the total interest paid so far.
- [ ] The `totalPaidPayments` method, which should return the total amount paid so far.
- [ ] The `interestSaved` method, which should return the total interest saved by making extra payments.
- [ ] The `paymentsSaved` method, which should return the total number of payments saved by making extra payments.
- [ ] The `totalPaymentCount` method, which should return the total number of payments for the loan.
- [ ] The `totalExpectedPaymentCount` method, which should return the total number of payments for the loan.
- [ ] The `createPayments` method, which has comments explaining the remaining functionality required.

You should not implement the `oneTimePayment` method yet! That will be saved for the next phase.

The `Payment` classes are used to represent a single payment in the loan. Each payment has a number of properties that should not be modified once the `Payment` instance is created. You will need to **encapsulate** the class so that the properties are not directly accessible except through getters.

- [ ] Finish implementing the `Payment` class by providing appropriate getters for the properties.

When you have finished all the parts of Part 1, you can submit your code on GradeScope per usual. Make sure to test your code thoroughly before submitting!

## Phase 2: Loan Calculator UI
The Loan class is complete, except for one method:

**oneTimePayment** – This method will pass in PaymentNumber and lumpSumAmount and should
- [ ] Make a new array of Payments, copying over all the payments < PaymentNumber
- [ ] Edit the payment in place, changing Principle Amount, Remaining Balance and Extra Payment, adding it to the array of

**Payments**
- [ ] Calculating all future Payments (adjusting for the new remaining balance)
The general structure of the application is set- MainComponent has LoanEntryComponent, and each payment will have a PaymentDisplayComponent.

**LoanEntryComponent**
- [ ] LoanEntryComponent.css – Should be complete, you may want to tweak the css for styling
- [ ] LoanEntryComponent.html – Look for ‘Fix Me’ and add spans/input fields for attributes
- [ ] LoanEntryComponent.ts – Look for ‘Fix Me’
- [ ] I’ve left in a few of the correct bindings (example, Total-Payments binding is correct).  Complete the rest of the bindings correctly.  
- [ ] Complete cleanLoanTable – This should remove all the loanTable components
- [ ] Complete calculate() – This method is fired when the ‘Calculate’ button is pressed in the application
- [ ] Complete PaintLoanSummary() – This method completes the top right portion of the screen
- [ ] Complete PaintPayments() – This method will draw all of the payments on the screen.  You’ll have to add a notifier for ExtraPayment changed

**PaymentDisplayComponent**
- [ ] PaymentDisplayComponent.css – Should be complete, you may want to tweak the css for styling
- [ ] PaymentDisplayComponent.html – Look for ‘Fix Me’ and add spans/input fields for attributes
- [ ] PaymentDisplayComponent.ts – Look for ‘Fix Me’
- [ ] I’ve left in a few of the correct bindings (example, idEndingBalance binding is correct).  Complete the rest of the bindings correctly.  
- [ ] Add the notifier and change event for ExtraPayments.  Changing extra payments should fire an event in LoanEntryComponent
The unit tests have been adjusted to test oneTimePayment.

The autograder will assign a portion of the grade for the automated test results.  The second portion of the grade will be assigned by the TAs/myself testing your published page.

## Code Quality Grading

Once you are finished with your project code, check over the following:

* Chosen good variable/function/class names (clear, concise, consistent, conventional, and correct)
* Included good jsdoc documentation for your classes, functions, and methods.
* Decomposed complicated functions with helper functions
* Decomposed components into ways that make sense (not too massive, but also not unnecessary ones)
* Avoided global state (e.g., a global variable). Global *constants* and top-level functions are fine, but storing data in a mutable global variable is bad practice.

Make sure your program and website runs; **broken programs do not earn points.**

## Help Resources

You will need to make effective use of the help resources we have available.

- [Documentation for Webz](https://boots-edu.github.io/webz/)

<!--- Example Webz applications:
  - [Task List](https://gsilber.github.io/WebEZ/example) ([source code](https://github.com/gsilber/WebEZ/tree/main/WebEZ-Example))
  - [Movies](https://gsilber.github.io/WebEZ/movies) ([source code](https://github.com/gsilber/WebEZ/tree/main/movies))
  - [Lander](https://gsilber.github.io/WebEZ/lander) ([source code](https://github.com/gsilber/WebEZ/tree/main/lander))
  - [Pong](https://gsilber.github.io/WebEZ/webpong) ([source code](https://github.com/gsilber/WebEZ/tree/main/web-pong))
- Good resources for HTML:
  - [MDN Tutorial](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
  - [W3 Schools Reference](https://www.w3schools.com/tags/default.asp)
- Good resources for CSS:
  - [MDN Tutorial](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/Getting_started)
  - [W3 Schools Reference](https://www.w3schools.com/cssref/index.php)-->

Be cautious in how much help you accept, since you will need to be able to explain and justify every line you submit - if you don't understand something, you need to learn how it works before you can use it!

## Frequently Asked Questions (FAQ)

Any commonly recurring questions will be answered here.

**Q:** *Can I modify the `tsconfig.json`, `.eslintrc.js`, or `.github/workflows/deploy.yml` files?*\
**A:** Tampering with the core infrastructure of the project (e.g., to turn off linting rules) is technically a form of academic dishonesty. Do not modify these files without permission by the instructor. Modifying them can be easily detected on our end and may be reported if it is done to bypass course requirements (e.g., disabling the `No Any Type` rule in the linter). Some files are perfectly fine to modify (e.g., `package.json`, `package-lock.json`) and others you are even invited to modify (e.g., `styles.css`). If you are unsure about whether you can modify a file, just ask!

**Q:** *Am I allowed to use other libraries instead of WebEz?*\
**A:** No, you must use WebEz for this project. We have not covered other libraries in this course, and we want to ensure that you are able to complete the project with the tools we have provided. If you have a specific need that you think WebEz cannot meet, please ask your TA or instructor for help. Note that abusing HTML manipulating code using JQuery or the DOM API (`document.querySelector`) is also not allowed. *(Added 5/7/24 at 9:51am)*

**Q:** *What is this `Diagram` tab that appears in my deployed site's `docs` page?*\
**A:** The `Diagram` tab is a new feature that shows a diagram of the components in your application. This is a feature of WebEz that we have not covered in class, but it is a useful tool for understanding the structure of your application. The boxes are each of your Component classes; solid lines are drawn between fields composing other components, and dashed lines are drawn between references made through local variables, parameters, and return values. You can ignore this tab if you like, but it may be helpful for understanding how your components are connected. Although you will not be graded directly on the diagram, the graders may use it to more quickly understand the structure of your website as they review your code. If you think that the  diagram is inaccurate, then you can contact Dr. Bart ([acbart@udel.edu](acbart@udel.edu)) with bug reports. *(Added 5/7/24 at 12:15pm)*


## Change Log

We'll keep track of changes to the project in this Change Log, in case we have to make significant changes or clarifications.

* Version 0.0.1 (11/7/24 at 10:39am): Initial version posted
