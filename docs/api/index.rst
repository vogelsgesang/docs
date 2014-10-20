API
===

The API provides programmatic access to all data and functions. It provides endpoints for managing users, projects, remotes, branches, snapshots, file revisions, issues and diffs.

.. toctree::
    :maxdepth: 2

    Authorization <authorization>
    Users <users>
    Projects <projects>
    Remotes <remotes>
    Branches <branches>
    Snapshots <snapshots>
    File Revisions <file_revisions>
    Issues <issues>
    Diffs <diffs>


Example API Call
----------------

.. http:get:: /example

   An example

   **Request headers**:

   .. sourcecode:: http

      Auhorization: Bearer 751cfa32f2b44cbba0c8e53a831657f9

   **Response headers**:

   .. sourcecode:: http

      Access-Control-Allow-Origin: *
      Access-Control-Allow-Credentials: true
      Access-Control-Allow-Methods: GET
      Access-Control-Allow-Headers: Authorization, X-PINGOTHER, Origin, Accept
      Access-Control-Max-Age: 1728000
      Cache-Control: no-cachei
