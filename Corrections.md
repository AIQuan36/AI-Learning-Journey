# Python Learning Journey — Corrections Log

## Chapter 1: Python Fundamentals

**Status:** COMPLETE  
**Final Project:** Personal Financial Decision System  
**Assessment:** PASSED

---

# Chapter 1 — Final Assessment Corrections

## Correction 1: Savings Goal Calculation

### Original Code
```python
amount_remaining_to_reach_savings_goal = (savings_goal - current_savings_balance) / monthly_savings_contribution
```

### Problem
The calculation determined the number of months needed to reach
the savings goal rather than the dollar amount remaining after
12 months.

### Corrected Code
```python
amount_remaining_to_reach_savings_goal = savings_goal - projected_savings_balance_after_12_months
```

### Lesson Learned
A calculation must match the information being requested.

---

## Correction 2: Projected Debt Balance

### Original Code
```python
projected_debt_balance = current_debt_balance + total_debt_payment
```

### Problem
Monthly debt payments were being added to the debt balance
instead of subtracted.

### Corrected Code
```python
projected_debt_balance = current_debt_balance - total_debt_payment
```

### Lesson Learned
Understanding the financial relationship between variables
is just as important as understanding Python syntax.

---

## Correction 3: Debt Payoff Timeline

### Original Code
```python
estimated_months_needed = current_debt_balance - projected_debt_balance
```

### Problem
Subtracting two debt balances calculates a dollar amount,
not the number of months needed to repay the debt.

### Intermediate Attempt
```python
estimated_months_needed = (current_debt_balance - projected_debt_balance) / monthly_debt_payment
```

This calculated the number of months represented by the
projected payments rather than the full repayment timeline.

### Corrected Code
```python
estimated_months_needed = current_debt_balance / monthly_debt_payment
```

### Lesson Learned
Dividing the total debt balance by the monthly payment
estimates the repayment timeline when interest is excluded.

---

## Correction 4: Monthly Cash Flow Conditions

### Original Code
```python
elif money_remaining_after_debt > 1000:
    print("Positive Cash Flow")
```

### Intermediate Attempt
```python
elif money_remaining_after_debt < 1000:
    print("Positive Cash Flow")
```

### Problem
The first condition was unreachable because the preceding
`if` statement already captured amounts of $1,000 or more.

The second attempt included zero and negative amounts,
causing incorrect classifications.

### Corrected Code
```python
if money_remaining_after_debt >= 1000:
    print("Strong Cash Flow")
elif money_remaining_after_debt > 0:
    print("Positive Cash Flow")
elif money_remaining_after_debt == 0:
    print("Break Even Cash Flow")
else:
    print("Negative Cash Flow")
```

### Lesson Learned
Python evaluates conditional statements from top to bottom.

The order and boundaries of conditions determine which
branch executes.

---

## Correction 5: Purchase Affordability

### Original Code
```python
elif money_remaining_after_purchase > 0:
    print("Purchase is Affordable")
```

### Problem
A purchase leaving exactly $0 was incorrectly classified
as unaffordable.

### Corrected Code
```python
elif money_remaining_after_purchase >= 0:
    print("Purchase is Affordable")
```

### Lesson Learned
Boundary values matter.

Using `>=` instead of `>` allows zero to be included
when the requirements specify it.

---

## Correction 6: Savings Goal Percentage

### Original Code
```python
if projected_savings_balance_after_12_months >= 100:
```

### Problem
The program compared a dollar balance against percentage
thresholds.

### Corrected Code
```python
if projected_savings_progress >= 100:
```

### Lesson Learned
Conditional comparisons must use the correct measurement.

Dollar amounts and percentages represent different information.

---

## Correction 7: Savings Classification Messages

### Original Messages
```python
print("Savings Goal Almost Reached")
print("Savings Goal Almost There")
```

### Corrected Messages
```python
print("Savings Goal Almost Achieved")
print("Savings Goal Halfway There")
```

### Lesson Learned
Program output should match the project requirements.

Even when the underlying logic is correct, wording matters.

---

# Chapter 1 — Key Debugging Lessons

1. Verify that calculations answer the intended question.
2. Understand relationships between financial variables.
3. Check whether results represent dollars, months, or percentages.
4. Evaluate conditional statements from top to bottom.
5. Test boundary values, especially zero.
6. Use the correct variables in comparisons.
7. Verify program output against the requirements.

---

# Chapter 1 — Final Assessment

**Project:** Personal Financial Decision System

**Result:** PASSED

### Skills Demonstrated

- Variables
- Data types
- User input
- Type conversion
- Arithmetic operations
- Financial calculations
- Conditional statements
- Comparison operators
- Variable reuse
- Program organization
- Independent debugging

### Final Reflection

Chapter 1 demonstrated progression from basic Python
instructions to a complete financial decision program.

The most important achievement was learning to identify,
understand, and independently correct programming mistakes.

---

**Next Chapter:** Chapter 2

---

# Chapter 2 — Lesson 2: Working With Lists

## Mini-projects

- **Transaction Review (100/100).** Trace which transactions a slice selects and check the list after each update.
- **Savings & Investment Analyzer (100/100).** Calculate savings goal progress as accumulated savings divided by the goal, multiplied by 100.
- **Debt Reduction System (100/100).** Keep the target debt, original total debt, and remaining debt in separate variables. Subtract the payment from the current debt to get the remaining debt. Divide the amount eliminated by the original total debt and multiply by 100 to measure progress.

## Final assessment — Personal Financial Portfolio Audit & Recovery System

**First submission:** 94/100  
**Final score:** 100/100

### Account updates and output

- I traced `account_balances[0] = account_balances` to an assignment that put the entire list into its first slot. I replaced it with `account_balances[0] = deposit` to store the numeric balance and applied the same approach to the withdrawal account.
- I moved both assignments before printing so the output showed the updated balances.
- I reused `monthly_savings_contribution` in place of the hard-coded deposit amount of `750`.
- The final review suggested optional reporting labels. “Balance After Deposit” and “Balance After Withdrawal” describe the resulting balances of $2,550 and $5,600. “Transaction Percentage Change” describes the combined effect of both transactions.

### Slicing

I changed `[3:]` to `[2:]` to include the third item. Python's zero-based index for that item is 2.

### Financial formulas

I used separate variables for the beginning ($20,700), adjusted ($22,000), and ending ($22,250) portfolio balances. Each percentage uses the reference value for the question it answers.

| Measurement | Calculation |
| --- | --- |
| Transaction percentage change | Net cash change ÷ adjusted portfolio balance × 100 |
| Overall portfolio percentage change | Overall dollar change ÷ beginning portfolio balance × 100 |
| Portfolio goal progress | Ending portfolio balance ÷ portfolio goal × 100 |

### Debugging process

I ran the code throughout development in PyCharm and checked the results against the project requirements and my expected values. When something was off, I reread the relevant line, traced what each variable held, made a focused correction, and reran the program.

**Next lesson:** Chapter 2, Lesson 3 — Introduction to `for` Loops.
