
Tags - to control which tests to run - applied to feature/scenario/ --tags - combinations
--tags=a,b  -> a or b (logical OR)
--tags=a --tags=b -> both a and b (logican AND)
--tags=~a -> not a -> NOT

## Add a tag to the feature file

Copy or type this code into `weekend.feature`:

<pre class="file" data-filename="weekend.feature" data-target="replace">
Feature: Is it nearly weekend?
  Everybody wants to know if it's nearly weekend yet

  Background:
    Given this step passes

  @tagged
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
