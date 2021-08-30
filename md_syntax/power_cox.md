## Syntax

Compute sample size

`power cox` \[`b1`\] \[`, power(numlist) options`\]

Compute power

`power cox` \[`b1`\]`, n(numlist)` \[`options`\]

Compute effect size (target regression coefficient)

`power cox, n(numlist) power(numlist)` \[`options`\]

where `b1` is the hypothesized regression coefficient (effect size) of a
covariate of interest in a Cox proportional hazards model desired to be
detected by a test with a prespecified power. `b1` may be specified
either as one number or as a list of values in parentheses (see
[<strong>numlist</strong>](http://www.stata.com/help.cgi?numlist)).

| options                                                                                                                                                                                                                                                                                                                                                   |                                       | Description                                                                                                                                                                                |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Main                                                                                                                                                                                                                                                                                                                                                      |                                       |                                                                                                                                                                                            |
| \*                                                                                                                                                                                                                                                                                                                                                        | `alpha(numlist)`                      | significance level; default is `alpha(0.05)`                                                                                                                                               |
| \*                                                                                                                                                                                                                                                                                                                                                        | `power(numlist)`                      | power; default is `power(0.8)`                                                                                                                                                             |
| \*                                                                                                                                                                                                                                                                                                                                                        | `beta(numlist)`                       | probability of type II error; default is `beta(0.2)`                                                                                                                                       |
| \*                                                                                                                                                                                                                                                                                                                                                        | `n(numlist)`                          | sample size; required to compute power or effect size                                                                                                                                      |
|                                                                                                                                                                                                                                                                                                                                                           | `nfractional`                         | allow fractional sample sizes                                                                                                                                                              |
| \*                                                                                                                                                                                                                                                                                                                                                        | `hratio(numlist)`                     | hazard ratio (exponentiated `b1`) associated with a one-unit increase in covariate of interest; specify instead of the regression coefficient `b1`; default is `hratio(0.5)`               |
| \*                                                                                                                                                                                                                                                                                                                                                        | `sd(numlist)`                         | standard deviation of covariate of interest; default is `sd(0.5)`                                                                                                                          |
| \*                                                                                                                                                                                                                                                                                                                                                        | `r2(numlist)`                         | squared coefficient of multiple correlation with other covariates; default is `r2(0)`                                                                                                      |
| \*                                                                                                                                                                                                                                                                                                                                                        | `eventprob(numlist)`                  | overall probability of an event (failure) of interest; default is `eventprob(1)`, meaning no censoring                                                                                     |
| \*                                                                                                                                                                                                                                                                                                                                                        | `failprob(numlist)`                   | synonym for `eventprob()`                                                                                                                                                                  |
| \*                                                                                                                                                                                                                                                                                                                                                        | `wdprob(numlist)`                     | proportion of subjects anticipated to withdraw from the study; default is `wdprob(0)`                                                                                                      |
|                                                                                                                                                                                                                                                                                                                                                           | `effect(effect)`                  | specify the type of effect to display; default is `effect(coefficient)`                                                                                                                    |
|                                                                                                                                                                                                                                                                                                                                                           | `direction`(`lower`\|`upper`)         | direction of the effect for effect-size determination; default is `direction(lower)`, which means that the postulated value of the parameter is smaller than the hypothesized value        |
|                                                                                                                                                                                                                                                                                                                                                           | `onesided`                            | one-sided test; default is two sided                                                                                                                                                       |
|                                                                                                                                                                                                                                                                                                                                                           | `parallel`                            | treat number lists in starred options or in command arguments as parallel when multiple values per option or argument are specified (do not enumerate all possible combinations of values) |
| Table                                                                                                                                                                                                                                                                                                                                                     |                                       |                                                                                                                                                                                            |
|                                                                                                                                                                                                                                                                                                                                                           | \[`no`\]`table`\[`(tablespec)`\]  | suppress table or display results as a table; see [<strong>[PSS]</strong> power, table](http://www.stata.com/help.cgi?power_opttable)                           |
|                                                                                                                                                                                                                                                                                                                                                           | `saving(filename`\[`, replace`\]`)` | save the table data to `filename`; use `replace` to overwrite existing `filename`                                                                                                          |
| Graph                                                                                                                                                                                                                                                                                                                                                     |                                       |                                                                                                                                                                                            |
|                                                                                                                                                                                                                                                                                                                                                           | `graph`\[`(graphopts)`\]          | graph results; see [<strong>[PSS]</strong> power, graph](http://www.stata.com/help.cgi?power_optgraph)                                                          |
|                                                                                                                                                                                                                                                                                                                                                           | `notitle`                             | suppress the title                                                                                                                                                                         |
| \* Specifying a list of values in at least two starred options, or at least two command arguments, or at least one starred option and one argument results in computations for all possible combinations of the values; see [<strong>numlist</strong>](http://www.stata.com/help.cgi?numlist). Also see the `parallel` option. |                                       |                                                                                                                                                                                            |
| `notitle` does not appear in the dialog box.                                                                                                                                                                                                                                                                                                              |                                       |                                                                                                                                                                                            |

| effect |               | Description                                 |
|--------|---------------|---------------------------------------------|
|        | `coefficient` | regression coefficient, `b1`; the default   |
|        | `hratio`      | hazard ratio, exp(`b1`)                     |
|        | `lnhratio`    | log hazard-ratio; synonym for `coefficient` |

where `tablespec` is

`column`\[`:label`\] \[`column`\[`:label`\] \[...\]\] \[`,`
`tableopts`\]

`column` is one of the columns defined below, and `label` is a column
label (may contain quotes and compound quotes).

| column                                                                                                            |            | Description                               |
|-------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------|
|                                                                                                                   | `alpha`    | significance level                        |
|                                                                                                                   | `power`    | power                                     |
|                                                                                                                   | `beta`     | type II error probability                 |
|                                                                                                                   | `N`        | number of subjects                        |
|                                                                                                                   | `delta`    | effect size                               |
|                                                                                                                   | `E`        | total number of events (failures)         |
|                                                                                                                   | `b1`       | regression coefficient                    |
|                                                                                                                   | `hratio`   | hazard ratio                              |
|                                                                                                                   | `lnhratio` | log hazard-ratio                          |
|                                                                                                                   | `sd`       | standard deviation                        |
|                                                                                                                   | `R2`       | squared multiple-correlation coefficient  |
|                                                                                                                   | `Pr_E`     | overall probability of an event (failure) |
|                                                                                                                   | `Pr_w`     | probability of withdrawals                |
|                                                                                                                   | `target`   | target parameter; synonym for `b1`        |
|                                                                                                                   | `_all`     | display all supported columns             |
| Column `beta` is shown in the default table in place of column `power` if option `beta()` is specified.           |            |                                           |
| Column `b1` is shown in the default table in place of column `hratio` when a regression coefficient is specified. |            |                                           |
| Columns `R2` and `Pr_w` are shown in the default table only if specified.                                         |            |                                           |