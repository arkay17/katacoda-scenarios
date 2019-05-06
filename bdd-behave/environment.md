
Setup and teardown -
Setup - set of actions taken before each step/scenario/feature/tag, like creating db, files, logging setup
Teardown – cleanup the setup or actions to take after each step/scenario/feature/tag
Behave supports this by implementing a file created by user - environment.py – same directory level as the steps 

## Add environmental controls

Copy or type this code into `environment.py`:

<pre class="file" data-filename="environment.py" data-target="replace">
from behave import fixture, use_fixture

@fixture
def days(context):
    context.days = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday']

@fixture
def weekend(context):
    context.weekend = ['Saturday', 'Sunday']

def before_all(context):
    context.config.setup_logging(
            format='%(asctime)s %(name)-25s %(lineno)-5d %(levelname)-8s %(message)s',
            datefmt='%a, %d %b %Y %H:%M:%S')
    use_fixture(days, context)
    use_fixture(weekend, context)

def after_scenario(context, scenario):
    print("Scenario {} ends here".format(scenario.name))

def after_feature(context, feature):
    print("Feature {} ends here".format(feature.name))

</pre>


