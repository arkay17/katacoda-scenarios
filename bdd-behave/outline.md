
Scenario outline - better organization, less gherkin and group test cases, when run same test with different parameters
No need to repeat steps with different parameters	

## Modify the feature file to use a scenario outline 

Copy or type this code into `weekend.feature`:

<pre class="file" data-filename="weekend.feature" data-target="replace">
Feature: Is it nearly weekend?
  Everybody wants to know if it's nearly weekend yet

  Scenario Outline: It'a &ltday_today&gt, is it weekend yet
    Given today is &ltday_today&gt
    And &ltday_today&gt is a valid day
    When I ask if it's weekend yet
    Then I should be told <response>

    Examples: all
      | day_today  |  response |
      | Wednesday  |  No       |
      | Saturday   |  Yes      |
      | Friday     |  TGIF     |
      | Monday     |  No       |
       
</pre>

