Installation
------------
The stable version can be used in two ways: as a system/user library through pip, or as a docker image.

The docker image is the recommended way because it is self-contained and isolated from the system, which means:

  * Downloading and using it is just one command
  * All dependencies are included
  * It is OS-independent (MacOS, Windows, GNU/Linux)
  * Several versions may coexist in the same machine without additional virtual environments

Additionally, you may create your own docker image with your custom plugins, ready to be used by others.


Through PIP
***********

.. code:: bash

   pip install --user senpy

   
Alternatively, you can use the development version:
 
.. code:: bash

   git clone git@github.com:gsi-upm/senpy
   cd senpy
   pip install --user .

If you want to install senpy globally, use sudo instead of the ``--user`` flag.

Docker Image
************
Build the image or use the pre-built one:   

.. code:: bash

   docker run -ti -p 5000:5000 gsiupm/senpy --host 0.0.0.0 --default-plugins

To add custom plugins, use a docker volume: 
    
.. code:: bash

   docker run -ti -p 5000:5000 -v <PATH OF PLUGINS>:/plugins gsiupm/senpy --host 0.0.0.0 --default-plugins -f /plugins
 

Python 2
........

There is a Senpy version for python2 too:
    
.. code:: bash

   docker run -ti -p 5000:5000 gsiupm/senpy:python2.7 --host 0.0.0.0 --default-plugins


Alias
.....

If you are using the docker approach regularly, it is advisable to use a script or an alias to simplify your executions:

.. code:: bash

   alias senpy='docker run --rm -ti -p 5000:5000 -v $PWD:/senpy-plugins gsiupm/senpy --default-plugins'


Now, you may run senpy from any folder in your computer like so:

.. code:: bash

   senpy --version
