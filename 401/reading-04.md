# Python Testing with pytest: Fixtures and Coverage
## Fixtures
You'll want to have some objects available to all of your tests.
Those objects might contain data you want to share across tests, or they might involve the network or filesystem. 
These are often known as "fixtures" 
you define fixtures using a combination of the pytest.fixture decorator
you don't invoke it with parentheses, but it's actually a function under the hood
the fixture, in contrast with regular-old data, can make calculations and decisions
if you set the scope of the fixture to be "module", it'll be available throughout your tests but will execute only a single time
You can do this by passing the scope parameter to the @pytest.fixture decorator:
