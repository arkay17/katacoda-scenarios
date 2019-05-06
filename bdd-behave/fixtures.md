
Variable 'context' is an instance of a class - used to store contextual data during the run 
Context persists within the scenario only - not between scenarios

Config/fixtures can be used – similar to pytest fixtures

## Add fixtures 

Copy or type this code into `behave_fixtures.py`:

<pre class="file" data-filename="environment.py" data-target="replace">
from behave import fixture

@fixture
def days(context):
    context.days = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'] 

@fixture
def weekend(context):
    context.weekend = ['Saturday', 'Sunday'] 
</pre>

## Add common steps - grouped to avoid duplication 

<pre class="file" data-filename="common_steps.py" data-target="replace">
import behave

@given('this step passes')
def step_impl(context):
    print("background step passed")
</pre>
