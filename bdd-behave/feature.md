
Gherkin written by Stakeholders - product owners, project managers are passed on to automation engineers for coding

BDD consists of
- Steps (Give, When, Then) - located in feature files (.feature)
- Step definitions - located in python files (.py)

## Create a feature file using Gherkin format

Feature file has one or more scenarios - feature name/scenario name/steps
- Precondition - 'given'
- Interaction to do something - 'when'
- Verify the expectation - 'then'

Copy or type this code into `weekend.feature`:

<pre class="file" data-filename="weekend.feature" data-target="replace">
Feature: Is it nearly weekend?
  Everybody wants to know if it's nearly weekend yet

  Scenario: Monday isn't weekend yet
    Given today is Monday
    When I ask if it's weekend yet
    Then I should be told "No"

  Scenario: Friday is nearly weekend
    Given today is Friday
    When I ask if it's weekend yet
    Then I should be told "Yes"

  Scenario: Wednesday isn't weekend yet
    Given today is Wednesday
    When I ask if it's weekend yet
    Then I should be told "No"

  Scenario: Saturday is already weekend
    Given today is Saturday
    When I ask if it's weekend yet
    Then I should be told "Yes"

</pre>

