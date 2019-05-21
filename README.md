# Welcome to Kaa Python SDK

Current version of Kaa Python SDK covers authentication management and provides programmatic access for timeseries REST API.

# Supported python versions

Python 3.6 and higher

# How to use

### Step 1 - Set credentials

```python
from kaa_sdk.config import set_credentials_file, set_config_file

set_credentials_file(uname='<YOUR_LOGIN>',
                     password='<YOUR_PASSWORD>',
                     client_id='<YOUR_CLIENT_ID>',
                     client_secret='<YOUR_CLIENT_SECRET>')
set_config_file(host='<KAA_HOST>',
                    auth_host='<KEYCLOAK_HOST>',
                    realm='<REALM>')
```

### Step 2 - explore available commands

#### Examples:

##### Get configs
```python
from kaa_sdk.epts.v1.api import get_time_series_config

get_time_series_config()

```

##### Get last time series
```python
from kaa_sdk.epts.v1.api import get_last_time_series

get_last_time_series("<APPLICATION_ID>", ["humidity", "temperature"])

```

##### Get time series
```python
from datetime import datetime, timedelta

from kaa_sdk.epts.v1.api import get_time_series

now = datetime.now()
then = now - timedelta(days=2)
json_resp = get_time_series("<APPLICATION_ID>", ["humidity"], then, now, ["<ENDPOINT_ID>"], "ASC")

```

### Also help available for each command

#### Examples:

```
help(get_time_series_config)

Help on function get_time_series_config in module kaa_sdk.epts.v1.api:

get_time_series_config(application_names=None)
    Returns configurations of all time series.
    
    :param application_names: Application name, one or multiple. If not specified,
     the data is returned for all available applications.
    :return: json with time series configuration
```
