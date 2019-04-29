## Modify the feature file to use a scenario outline 

Copy or type this code into `weekend.feature`:

<pre class="file" data-filename="weekend.feature" data-target="replace">
Feature: Is it nearly weekend?
  Everybody wants to know if it's nearly weekend yet

  Scenario Outline: <day_today> isn't weekend yet
    Given today is <day_today>
    When I ask if it's weekend yet
    Then I should be told <response>

    Examples :
      | day_today  |  response |
      | Wednesday  |  No       |
      | Saturday   |  Yes      |
      | Friday     |  TGIF     |
      | Monday     |  No       |
       
</pre>

