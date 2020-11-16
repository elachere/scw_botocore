botocore
========

This repository is a fork from [botocore](https://github.com/boto/botocore) meant to work with [Scaleway S3 Buckets](https://www.scaleway.com/fr/object-storage/)

Getting Started
---------------
Assuming that you have Python and ``virtualenv`` installed, set up your environment and install the required dependencies like this or you can install the library using ``pip``:

.. code-block:: sh

    $ git clone https://github.com/boto/botocore.git
    $ cd botocore
    $ virtualenv venv
    ...
    $ . venv/bin/activate
    $ pip install -r requirements.txt
    $ pip install -e .
    
Using Botocore
~~~~~~~~~~~~~~
After installing botocore 

Next, set up credentials (in e.g. ``~/.aws/credentials``):

.. code-block:: ini

    [default]
    aws_access_key_id = YOUR_KEY
    aws_secret_access_key = YOUR_SECRET

Then, set up a default region (in e.g. ``~/.aws/config``):

.. code-block:: ini

   [default]
   region=us-east-1
    
Other credentials configuration method can be found `here <https://boto3.amazonaws.com/v1/documentation/api/latest/guide/credentials.html>`__

Then, from a Python interpreter:

.. code-block:: python

    >>> import botocore.session
    >>> session = botocore.session.get_session()
    >>> client = session.create_client('ec2')
    >>> print(client.describe_instances())

