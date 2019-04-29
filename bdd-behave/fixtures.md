## Add fixtures and common steps

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


<pre class="file" data-filename="common_steps.py" data-target="replace">
import behave

@given('the {day_today} is a valid day')
def step_impl(context, day_today):
    assert day_today in context.days
</pre>
