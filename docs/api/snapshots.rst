Snapshots
=========

.. automodule:: api.v1.snapshot
    :members:

.. http:get:: /project/<project_id>/snapshot/<snapshot_id>

   The posts tagged with `tag` that the user (`user_id`) wrote.

   **Example request**:

   .. sourcecode:: http

      GET /project/<project_id>/snapshot/<snapshot_id> HTTP/1.1
      Host: quantifiedcode.org
      Accept: application/json
      Auhorization: Bearer 751cfa32f2b44cbba0c8e53a831657f9

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json
      Access-Control-Allow-Origin: *
      Access-Control-Allow-Credentials: true
      Access-Control-Allow-Methods: GET
      Access-Control-Allow-Headers: Authorization, X-PINGOTHER, Origin, Accept
      Access-Control-Max-Age: 1728000
      Cache-Control: no-cachei

      {
        "snapshot" : {
            ...
        },
      },

   :reqheader Accept: the response content type depends on
                      :mailheader:`Accept` header
   :reqheader Authorization: (optional) OAuth token to authenticate
   :resheader Content-Type: this depends on :mailheader:`Accept`
                            header of request
   :statuscode 200: no error

.. http:get:: /project/<project_id>/snapshot/<snapshot_id>/code/<regex(".*$"):path>

   The posts tagged with `tag` that the user (`user_id`) wrote.

   **Example request**:

   .. sourcecode:: http

      GET /project/<project_id>/snapshot/<snapshot_id>/code/<regex(".*$"):path> HTTP/1.1
      Host: quantifiedcode.org
      Accept: application/json
      Auhorization: Bearer 751cfa32f2b44cbba0c8e53a831657f9

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json
      Access-Control-Allow-Origin: *
      Access-Control-Allow-Credentials: true
      Access-Control-Allow-Methods: GET
      Access-Control-Allow-Headers: Authorization, X-PINGOTHER, Origin, Accept
      Access-Control-Max-Age: 1728000
      Cache-Control: no-cachei

      {
        "content" : {
            ...
        },
        "start" : 1,
        "end" : 2
      },

   :reqheader Accept: the response content type depends on
                      :mailheader:`Accept` header
   :reqheader Authorization: (optional) OAuth token to authenticate
   :resheader Content-Type: this depends on :mailheader:`Accept`
                            header of request
   :statuscode 200: no error
   :statuscode 500: invalid parameter

.. http:get:: /project/<project_id>/snapshot/<snapshot_id>/tree

   The posts tagged with `tag` that the user (`user_id`) wrote.

   **Example request**:

   .. sourcecode:: http

      GET /project/<project_id>/snapshot/<snapshot_id>/tree HTTP/1.1
      Host: quantifiedcode.org
      Accept: application/json
      Auhorization: Bearer 751cfa32f2b44cbba0c8e53a831657f9

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json
      Access-Control-Allow-Origin: *
      Access-Control-Allow-Credentials: true
      Access-Control-Allow-Methods: GET
      Access-Control-Allow-Headers: Authorization, X-PINGOTHER, Origin, Accept
      Access-Control-Max-Age: 1728000
      Cache-Control: no-cachei

      {
        "parent_path" : 1,
        "files" : 2,
        "path" : 3,
        "summary" : {
            "issues" : {}
        }
      },

   :reqheader Accept: the response content type depends on
                      :mailheader:`Accept` header
   :reqheader Authorization: (optional) OAuth token to authenticate
   :resheader Content-Type: this depends on :mailheader:`Accept`
                            header of request
   :statuscode 200: no error

.. http:get:: /project/<project_id>/snapshot/<snapshot_id>/code_objects

   The posts tagged with `tag` that the user (`user_id`) wrote.

   **Example request**:

   .. sourcecode:: http

      GET /project/<project_id>/snapshot/<snapshot_id>/code_objects HTTP/1.1
      Host: quantifiedcode.org
      Accept: application/json
      Auhorization: Bearer 751cfa32f2b44cbba0c8e53a831657f9

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json
      Access-Control-Allow-Origin: *
      Access-Control-Allow-Credentials: true
      Access-Control-Allow-Methods: GET
      Access-Control-Allow-Headers: Authorization, X-PINGOTHER, Origin, Accept
      Access-Control-Max-Age: 1728000
      Cache-Control: no-cachei

      {
        "code_objects" : [

        ],
        "count" : 5
      },

   :reqheader Accept: the response content type depends on
                      :mailheader:`Accept` header
   :reqheader Authorization: (optional) OAuth token to authenticate
   :resheader Content-Type: this depends on :mailheader:`Accept`
                            header of request
   :statuscode 200: no error
   :statuscode 500: invalid parameter

.. http:get:: /project/<project_id>/snapshot/<snapshot_id>/files

   The posts tagged with `tag` that the user (`user_id`) wrote.

   **Example request**:

   .. sourcecode:: http

      GET /project/<project_id>/snapshot/<snapshot_id>/files HTTP/1.1
      Host: quantifiedcode.org
      Accept: application/json
      Auhorization: Bearer 751cfa32f2b44cbba0c8e53a831657f9

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json
      Access-Control-Allow-Origin: *
      Access-Control-Allow-Credentials: true
      Access-Control-Allow-Methods: GET
      Access-Control-Allow-Headers: Authorization, X-PINGOTHER, Origin, Accept
      Access-Control-Max-Age: 1728000
      Cache-Control: no-cachei

      {
        "file_revisions" : [

        ],
        "count" : 5
      },

   :reqheader Accept: the response content type depends on
                      :mailheader:`Accept` header
   :reqheader Authorization: (optional) OAuth token to authenticate
   :resheader Content-Type: this depends on :mailheader:`Accept`
                            header of request
   :statuscode 200: no error
   :statuscode 500: invalid parameter

.. http:get:: /project/<project_id>/snapshot/<snapshot_id>/issues

   The posts tagged with `tag` that the user (`user_id`) wrote.

   **Example request**:

   .. sourcecode:: http

      GET /project/<project_id>/snapshot/<snapshot_id>/issues HTTP/1.1
      Host: quantifiedcode.org
      Accept: application/json
      Auhorization: Bearer 751cfa32f2b44cbba0c8e53a831657f9

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json
      Access-Control-Allow-Origin: *
      Access-Control-Allow-Credentials: true
      Access-Control-Allow-Methods: GET
      Access-Control-Allow-Headers: Authorization, X-PINGOTHER, Origin, Accept
      Access-Control-Max-Age: 1728000
      Cache-Control: no-cachei

      {
        "issues" : [

        ],
        "count" : 5
      },

   :reqheader Accept: the response content type depends on
                      :mailheader:`Accept` header
   :reqheader Authorization: (optional) OAuth token to authenticate
   :resheader Content-Type: this depends on :mailheader:`Accept`
                            header of request
   :statuscode 200: no error
   :statuscode 500: invalid query
