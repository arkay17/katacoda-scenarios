
Update the steps as per the latest feature file with the scenario outline

Copy or type this code into `weekend.py`:

<pre class="file" data-filename="weekend.py" data-target="replace">
#!/usr/bin/python
import behave

def check_weekend(weekend, today):
    if today == "Friday":
       return "TGIF"
    elif today in weekend:
        return "Yes"
    else:
        return "No"

@given('today is {day_today}')
def step_impl(context, day_today):
    context.today = day_today

@given('{day_today} is a valid day')
def step_impl(context, day_today):
    assert day_today in context.days

@when('I ask if it\'s weekend yet')
def step_impl(context):
    context.is_weekend = check_weekend(context.weekend, context.today)
    
@then('I should be told {response}')
def step_impl(context, response):
    assert context.is_weekend == response

</pre>

