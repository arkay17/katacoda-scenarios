## Create a feature file using Gherkin format

Copy or type this code into `TGIF.feature`:

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

