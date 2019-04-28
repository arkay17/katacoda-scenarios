## Implement the steps in the feature file

Copy or type this code into `weekend.py`:

<pre class="file" data-filename="weekend.py" data-target="replace">
#!/usr/bin/python
import behave

weekend = ['Friday', 'Saturday', 'Sunday']

def check_weekend(today):
    if today in weekend:
        return "Yes"
    else:
        return "No"

@given('today is Saturday')
def step_impl(context):
    context.today = "Saturday"

@given('today is Monday')
def step_impl(context):
    context.today = "Monday"

@given('today is Friday')
def step_impl(context):
    context.today = "Friday"

@given('today is Wednesday')
def step_impl(context):
    context.today = "Wednesday"

@when('I ask if it\'s weekend yet')
def step_impl(context):
    context.weekend = check_weekend(context.today)
    
@then('I should be told "Yes"')
def step_impl(context):
    assert context.is_weekend == "Yes"

@then('I should be told "No"')
def step_impl(context):
    assert context.is_weekend == "No"
</pre>

