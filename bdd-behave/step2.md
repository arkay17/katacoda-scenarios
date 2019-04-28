This is your second step.

## Task

This is an _example_ of creating a scenario and running a **command**

Copy or type this code into `TGIF.py`:

<pre class="file" data-filename="TGIF.py" data-target="replace">
#!/usr/bin/python
import behave

@given('today is Sunday')
def step_impl(context):
	print("Sunday")
</pre>


Copy or type this code into `TGIF.feature`:

<pre class="file" data-filename="TGIF.feature" data-target="replace">
Feature: Is it Friday yet?
  Everybody wants to know when it's Friday

  Scenario: Sunday isn't Friday
    Given today is Sunday
    When I ask whether it's Friday yet
    Then I should be told "Nope"

  Scenario: Friday is Friday
    Given today is Friday
    When I ask whether it's Friday yet
    Then I should be told "TGIF"
</pre>

