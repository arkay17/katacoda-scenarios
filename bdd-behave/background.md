
Background - another keyword - only one background in a feature file, placed before all scenarios 
These steps are run before any scenario in the feature, but after 'before scenario' setup in environment.py	

## Add a background to the feature file - implements before every scenario

Copy or type this code into `weekend.feature`:

<pre class="file" data-filename="weekend.feature" data-target="replace">
Feature: Is it nearly weekend?
  Everybody wants to know if it's nearly weekend yet

  Background: 
    Given this step passes

  Scenario Outline: It'a &ltday_today&gt, is it weekend yet
    Given today is &ltday_today&gt
    And &ltday_today&gt is a valid day
    When I ask if it's weekend yet
    Then I should be told &ltresponse&gt

    Examples: all
      | day_today  |  response |
      | Wednesday  |  No       |
      | Saturday   |  Yes      |
      | Friday     |  TGIF     |
      | Monday     |  No       |

</pre>
