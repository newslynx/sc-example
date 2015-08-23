
Sous Chefs
-------------
**sc-example** provides access to the following Sous Chefs

RUNS sc_example.SayMyName
Say My Name
~~~~~~~~~~~

-  Conveniently says your name.
-  This Sous Chef runs the python module ``sc_example.SayMyName``.
-  API Slug: ``say-my-name``

Development
^^^^^^^^^^^

Pass runtime options to ``say-my-name`` and stream output. **NOTE** Will
not execute the SousChef's ``load`` method.

.. code:: bash

    $ newslynx sc sc_example/say_my_name.yaml option=value1

Alternatively pass in a recipe file

.. code:: bash

    $ newslynx sc sc_example/say_my_name.yaml --recipe=recipe.yaml

API Usage
^^^^^^^^^

Add this Sous Chef to your authenticated org

.. code:: bash

    $ newslynx api sous-chefs create -d=sc_example/say_my_name.yaml

Create a Recipe with this Sous Chef with command line options.

.. code:: bash

    $ newslynx api recipes create sous_chef=say-my-name **options

Alternatively pass in a recipe file.

.. code:: bash

    $ newslynx api recipes create sous_chef=say-my-name --data=recipe.yaml

Save the outputted ``id`` of this recipe, and execute it via the API.
**NOTE** This will place the recipe in a task queue.

.. code:: bash

    $ newslynx api recipes cook id=<id>

Alternatively, run the Recipe, passing in arbitrary runtime options, and
stream it's output: **NOTE** Will not execute the SousChef's ``load``
method.

.. code:: bash

    $ newslynx api recipes cook id=<id> --passthrough **options

Options
^^^^^^^

In addition to default recipe options, ``say-my-name`` also accepts the
following

-  ``my_name``

   -  Your name

   -  **Required**
   -  Should be rendered with a ``text`` form.
   -  Accepts inputs of type:

      -  ``string``



