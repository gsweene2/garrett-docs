Node
======
.. meta::
   :description lang=en: Node docs


Where is npmrc?
---------------

.. code-block:: bash
  :linenos:

  $ npm config ls -l | grep 'npmrc'
  globalconfig = "/usr/local/etc/npmrc"
  userconfig = "/Users/<user>/.npmrc"

Where are my node packages?
---------------------------

.. code-block:: bash
  :linenos:

  npm list -g > node_packages.txt
 
  cat node_packages.txt
  
  /usr/local/lib
  ├─┬ @aws-amplify/cli@4.41.2
  │ ├─┬ amplify-app@2.20.8
  │ │ ├── amplify-frontend-android@2.14.4 deduped
  │ │ ├── amplify-frontend-ios@2.18.4 deduped
  │ │ ├── amplify-frontend-javascript@2.20.4 deduped
  │ │ ├── chalk@3.0.0 deduped
  │ │ ├── execa@4.1.0 deduped
  │ │ ├── fs-extra@8.1.0 deduped
  │ │ ├─┬ graphql@14.7.0
  │ │ │ └── iterall@1.3.0
  │ │ ├── ini@1.3.8 deduped
  │ │ ├── inquirer@7.3.3 deduped
  │ │ ├─┬ node-emoji@1.10.0
  │ │ │ └── lodash.toarray@4.4.0
