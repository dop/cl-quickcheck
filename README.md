# cl-quickcheck - a Common Lisp port of the QuickCheck unit test framework

# EXAMPLE

```
$ clisp example.lisp
Starting tests with seed #S(RANDOM-STATE #*1111111000010000101001011100110101100110011101010000110100110111)
...
ERROR (ISNT MONEY= (DOLLARS 'M) (FRANCS M))

=: M is not a number

  with values #S(MONEY :AMOUNT M :CURRENCY USD) #S(MONEY :AMOUNT -2 :CURRENCY FRANC)
  for ((M -2))
  100/100 counterexamples.
FAIL (IS MONEY= (DOLLARS M) (DOLLARS N))
  with values #S(MONEY :AMOUNT 11 :CURRENCY USD) #S(MONEY :AMOUNT -19 :CURRENCY USD)
  for ((M 11) (N -19))
  98/100 counterexamples.
  0 cases checked and passed in 100 attempts.
95 tests submitted; 2 FAILED.
```

See [example.lisp](https://github.com/mcandre/cl-quickcheck/blob/master/example.lisp) for more information.

# INSTALL

```
$ clisp
> (ql:quickload 'cl-quickcheck)
```

# REQUIREMENTS

* a [Common Lisp](http://www.cliki.net/Common%20Lisp%20implementation), such as `clisp`
* [Quicklisp](http://www.quicklisp.org/)

## Optional

* [ruby](https://www.ruby-lang.org/) 2+
* [Node.js](http://nodejs.org/) 0.8+
* [pargs](https://github.com/mcandre/pargs)
* [editorconfig-tools](https://www.npmjs.com/package/editorconfig-tools)

# DEVELOPMENT

## Testing

Ensure the example script works as expected:

```
$ bundle
$ cucumber
Feature: Run example tests

  Scenario: Running example tests            # features/run_example_tests.feature:3
    Given the program has finished           # features/step_definitions/steps.rb:1
    Then the output is correct for each test # features/step_definitions/steps.rb:5

1 scenario (1 passed)
2 steps (2 passed)
0m4.913s
```

Guard can automatically run testing when the code changes:

```
$ bundle
$ guard -G Guardfile-cucumber
...
```

## Linting

Keep the code tidy:

```
$ npm install
$ rake lint
...
```
