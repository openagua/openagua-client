# openagua-client
A very thin wrapper around the OpenAgua web API.

# Usage

To use this, you need an API key from OpenAgua. Once you have that, you can supply it from an environment variable called `OA_SECRET_KEY` or directly as an argument to the client.

Here are two examples demonstrating each approach.

___Example 1___

In this example, the API key is in the environment variable `OA_SECRET_KEY`. Note that this may be loaded dynamically using, for example, [dot_env](https://pypi.org/project/python-dotenv/)

```python
from openagua_client import Client as OA
oa = OA()
network = oa.get_network(77)
```

___Example 2___

The key is supplied directly. Note that it is best practice to never hard code secrets. Therefore, that is not done in this example, though technically it could be done. Using environment variables for keys is best practice.

```python
import os
from openagua_client import Client as OA
oa_api_key = os.environ['MY_OPENAGUA_API_KEY']
oa = OA(api_key=oa_api_key)
network = oa.get_network(77)
```
