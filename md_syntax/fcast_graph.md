## Syntax

`fcast graph`
[varlist](http://www.stata.com/help.cgi?varlist)
_\[`if`\] \[`in`\]_ \[`, options`\]

where `varlist` contains one or more forecasted variables generated by
[<strong>fcast compute</strong>](http://www.stata.com/help.cgi?fcast%20compute).

| Options                                    |                         | Description                                                                                                                                                           |
|--------------------------------------------|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Main                                       |                         |                                                                                                                                                                       |
|                                            | `differences`           | graph forecasts of the first-differenced variables (`vec` only)                                                                                                       |
|                                            | `noci`                  | suppress confidence bands                                                                                                                                             |
|                                            | `observed`              | include observed values of the predicted variables                                                                                                                    |
| Forecast plot                              |                         |                                                                                                                                                                       |
|                                            | `cline_options`         | affect rendition of the forecast lines                                                                                                                                |
| CI plot                                    |                         |                                                                                                                                                                       |
|                                            | `ciopts(area_options)`  | affect rendition of the confidence bands                                                                                                                              |
| Observed plot                              |                         |                                                                                                                                                                       |
|                                            | `obopts(cline_options)` | affect rendition of the observed values                                                                                                                               |
| Y axis, Time axis, Titles, Legend, Overall |                         |                                                                                                                                                                       |
|                                            | `twoway_options`        | any options other than `by()` documented in [<strong>[G-3]</strong> <em>twoway_options</em>](http://www.stata.com/help.cgi?twoway_options) |
|                                            | `byopts(by_option)`     | affect appearance of the combined graph                                                                                                                               |