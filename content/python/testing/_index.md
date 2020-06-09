+++
title = "Testing"
date = 2020-06-09T16:18:54+02:00
weight = 7

+++

## Mocking

Mock is useful when mocking the parameter passed into a specific class during the instantiation of the class. Then you can mock attributes of that parameter, which will be called instead of an actual parameter being passed to the contructor.

In the example below, the `gateway` is mocked and dummy data is given as the return value for the `get_something` method of the `gateway`. In this case, only the `get_upper_something` is unit tested, while the dependecies are mocked out.

```python
from unittest.mock import Mock

class Service():
    def __init__(self, gateway):
    	self.gateway = gateway

    def get_upper_something(self):
    	return gateway.get_something()

def test_get_upper_something():
	gateway = Mock()
    gateway.get_something.return_value = [1, 2]

    service = Service(gateway)
    service.get_upper_something()

    assert result == [1, 2]
```

