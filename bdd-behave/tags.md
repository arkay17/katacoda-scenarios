## Add a background to the feature file - implements before every scenario

Copy or type this code into `weekend.feature`:

<pre class="file" data-filename="weekend.feature" data-target="replace">
Feature: Is it nearly weekend?
  Everybody wants to know if it's nearly weekend yet

  Background: Validate input
    Given the \<day_today\> is a valid day

  @tagged
  Scenario Outline: \<day_today\> isn't weekend yet
    Given today is \<day_today\>
    When I ask if it's weekend yet
    Then I should be told \<response\>

  Examples :
    | day_today  |  response |
    | Wednesday  |  No       |
    | Saturday   |  Yes      |
    | Friday     |  TGIF     |
    | Monday     |  No       |

</pre>
