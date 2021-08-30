## Syntax

`procrustes (varlist_y) (varlist_x)` <span
class="command">\[`if`\] \[`in`\]_ \[`weight`\] \[`, options`\]

| Options                                                                                                                                                                            |                                | Description                                                            |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------|------------------------------------------------------------------------|
| Model                                                                                                                                                                              |                                |                                                                        |
|                                                                                                                                                                                    | `transform:(orthogonal)`   | orthogonal rotation and reflection transformation; the default         |
|                                                                                                                                                                                    | `transform:(oblique)`      | oblique rotation transformation                                        |
|                                                                                                                                                                                    | `transform:(unrestricted)` | unrestricted transformation                                            |
|                                                                                                                                                                                    | `noconstant`                   | suppress the constants                                                 |
|                                                                                                                                                                                    | `norho`                        | suppress the dilation factor rho (set rho=1)                           |
|                                                                                                                                                                                    | `force`                        | allow overlap and duplicates in `varlist_y` and `varlist_x` (advanced) |
| Reporting                                                                                                                                                                          |                                |                                                                        |
|                                                                                                                                                                                    | `nofit`                        | suppress table of fit statistics by target variable                    |
| `bootstrap`, `by`, `jackknife`, and `statsby` are allowed; see [<strong>prefix</strong>](http://www.stata.com/help.cgi?prefix).                         |                                |                                                                        |
| Weights are not allowed with the [<strong>bootstrap</strong>](http://www.stata.com/help.cgi?bootstrap) prefix.                                          |                                |                                                                        |
| `aweight`s are not allowed with the [<strong>jackknife</strong>](http://www.stata.com/help.cgi?jackknife) prefix.                                       |                                |                                                                        |
| `aweight`s and `fweight`s are allowed; see [<strong>weights</strong>](http://www.stata.com/help.cgi?weights).                                           |                                |                                                                        |
| See [<strong>[MV]</strong> procrustes postestimation](http://www.stata.com/help.cgi?procrustes_postestimation) for features available after estimation. |                                |                                                                        |