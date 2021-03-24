# tx
>tx is a test definition language in plain text format  
> updated: 20210321

** alpha version **
Feedback expected. Maybe no clone worthy. coments welcome [The tx Team](tx@bip.mx)

## background

tx (pronouced tex) is the compilation of several projects we've worked on through the years.

latest incarnations derive from the lisp concept of several equality comparators (=, eq, eql, equal, equalp, et al) and the inclusion of typed expected results. this in particular relates also to the =, == and === found in several languages, regarding to the interpretation.

the plain text aspect comes from two sources, first regarding the documentation of the tests (are they thorough?, are they sufficient?, should I use that?, ...); the domain aspect of the test, like testing for true, false, null and empty, testing for 0 to 32k, test for negatives or test the unexpected (random?); the third and probably noteworthy is the example of mobile development, multiplatform frameworks aside, say your developing an application for IOS and Android, if the application is the same (inside the platform parameters) shouldn't the tests applied be the same?

Also, why do you have to rewrite all your tests if you change test frameworks? in the same language, in different versions, in different platforms, for differet implementations?

tx would be us looking for an unambiguos result definition and detailed (stricter) results to have in the test results.

## tx the definition

tx is a test definition language in "plain" text. tx is a "meta" language that drive the test implemented in a particular programming language, level of test (functional, unit, user, etc.). Allowing the documentation of the tests lifecycle.

"plain" text refers of course of using plain text files. Yet we lean to give some hierarchy via symbolic expressions, because of the homoiconic definition.
"meta" refers as a recipe for implementing a test in a particular language or framework, either in the framework test definition language or natively in a tx implementation.

### use cases

*warning* the following is more a tool for thought, since there is no tx definition yet. meta tdd for the tdd tool.

> tx test
>> :
```
(^Function "x" should return an Integer^ x result-is-integer (input domain (-1 0 1))) ; for whatever reason -1 signals error
_! named parameters
(test-description function test-type input-domain)
_! introspect/show/document (meta level) the function/module documentation
_! when, who, how, where (machine, os, browser, versions, etc)
_! user input
_! input, output, expected status (pass, fail), function result,
```
>> :
```  
php         : gettype(x(1)) == 'integer'
javascript  : Number.isInteger(x(1))   // it think I found a bug in node. Number.isInteger(1.0) returns true?
lisp (sbcl) : (typep 1 'integer)
```
## goals

* make things simpler. reduce learning curve. be consistent over time.
* document test results over time
* document best practices
* templates?
* document the aligment of tests to a particular business or implmentation requirement.
* define hierarchy: suites, test, groups, domains, etc.
* handle exceptions, return values, messages, statuses??? stati?

## next actions

**keep on going**
