## Update the steps as per the outline

Copy or type this code into `weekend.py`:

<pre class="file" data-filename="weekend.py" data-target="replace">
#!/usr/bin/python
import behave

def check_weekend(today):
    if today == "Friday":
       return "TGIF"
    elif today in context.weekend:
        return "Yes"
    else:
        return "No"

@given('today is {day_today}')
def step_impl(context, day_today):
    context.today = day_today

@when('I ask if it\'s weekend yet')
def step_impl(context):
    context.is_weekend = check_weekend(context.today)
    
@then('I should be told {response}')
def step_impl(context, response):
    assert context.is_weekend == response

</pre>

