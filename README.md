# Cross_Sell_Hack
To make debugging of logistic_regression module easier we enable imported modules autoreloading feature.

By doing this you may change the code of logistic_regression library and all these changes will be available here.

%load_ext autoreload %autoreload 2

Add project root folder to module loading paths.

import sys sys.path.append('../..')

Some needful libraries

!pip install certifi==2019.11.28 !pip install Click==7.0 !pip install Flask==1.1.1 !pip install gunicorn==19.9.0 !pip install itsdangerous==1.1.0 !pip install Jinja2==2.10.1 !pip install MarkupSafe==1.1.1 !pip install Werkzeug==0.15.5 !pip install numpy>=1.9.2 !pip install scipy>=0.15.1 !pip install matplotlib>=1.4.3 !pip install pandas>=0.19 !pip install tpot>=0.11.0 !pip install seaborn==0.9.0 !pip install cloudpickle>=0.6.0 !pip install scikit-learn==0.20.0 !pip install joblib==0.14.0 !pip install xgboost

To save csv to local system from binder notebook

from IPython.display import HTML import base64

def create_download_link( df, title = "Download CSV file", filename = "data.csv"):
 csv = df.to_csv() b64 = base64.b64encode(csv.encode()) payload = b64.decode() html = '{title}' html = html.format(payload=payload,title=title,filename=filename) return HTML(html)
