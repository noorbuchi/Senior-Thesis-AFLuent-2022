**Outline:**
- Discuss SFL and state that it's the focus for this research
    - Briefly discuss various types other than coefficient based
    - Discuss each equation
        - Reason to pick
        - evaluation and results
        - drawbacks
        - Variations
    - TODO: add coefficient based table here
- Tools that implement SFL
    - Zoltar
    - CharmFL
- Combining approaches
- User friendliness
- FIXME: not sure what to add yet
- Evaluation?

# Survey of AFL

### Spectrum based section (general)

- **Definition of Similarity Coefficient**: "Intuitively, the closer the execution pattern of a statement
is to the failure pattern of all test cases, the more likely the
statement is to be faulty, and consequently the more suspicious the statement seems. By the same token, the farther the
execution pattern of a statement is to the failure pattern, the
less suspicious the statement appears to be. Similarity coef-
ficient-based measures can be used to quantify this closeness,
and the degree of closeness can be interpreted as the suspi-
ciousness of the statements." `page 8`

- "there is no technique claim- ing that it can outperform all others under every scenario. In
  other words, an optimum spectrum-based technique does not exist"
  - supported by `No pot of gold at the end of program spectrum rainbow: Greatest risk evaluation formula does not exist`

### Tarantula

- Coloring based suspiciousness (hue)
- Better performance than other such as set union and set intersection
  - Less code has to be analyzed by developer before fault is found
- Grouping Tarantula

### Ochiai

- surpass tarantula according to `An evaluation of similarity coefficients for software fault localization`
- "There are two major differences between Ochiai and the
nearest neighbor model"
  - The nearest neighbor model uti-
  lizes a single failed test case, while Ochiai uses multiple
  failed test cases,
  - The nearest neighbor model only
  selects the successful test case that most closely resembles
  the failed test case, while Ochiai includes all successful test
  cases
- Ochiai2: an extension of Ochiai
  - found in `A model for spectra-based software diagnosis`, Naish and Lee
- `Theory and practice, do they match? a case with spectrum-based fault localization`
  argues that Ochiai is better than O and O^p for programs with single bugs

### O and O^p
- found in `A model for spectra-based software diagnosis`, Naish and Lee
- O fpr single bug and O^p is for multiple bugs programs
- Naish and Lee suggest that its more effective than Tarantula, Ochiai, and
  Ochiai2 for programs with single bug

### DStar
- found in `The DStar method for effective software fault localization`
- Outperforms most coefficinents in most cases

## Issues

- Some pointed out in `Isolating suspiciousness from spectrum-based fault localization techniques,`
- Some pointed out in `A family of code coverage-based heuristics for effective fault localization`
- Risk is only calculated for suspicious statements, and unsus-
  picious statements are simply assigned the lowest value. It is
  possible, however, that successful test cases may also con-
  tain bugs.
- the contribution of the first failed test case that
  executes it in computing its suspiciousness is larger than or
  equal to that of the second failed test case that executes it,
  which in turn is larger than or equal to that of the third failed
  test case that executes it, and so on
- there is a high likelihood
  that the suspiciousness score assigned to these statements
  will be exactly the same
  - information related to statement execution frequency can be used to break ties
  - look into `Ties within fault localization rankings: Exposing and addressing the problem`
  - look into `Exploiting count spectra for Bayesian fault localization`
  - look into `Exploiting count spectra for Bayesian fault localization`
- All SFL assume that a reliably working test framework for the code exists
- Overhead issues
  - look into `A dynamic code coverage approach to maximize fault localization efficiency`


