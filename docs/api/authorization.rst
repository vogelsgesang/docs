Authorization
=============

There are two ways to authorize yourself with the QuantifiedCode API.

Either pass an Authorization header with your request or use an URL parameter.

Example: User Profile
---------------------

.. http:get:: /user

   Returns information for a User Document. (Email, connected Accounts, etc.)

   **Example request**:

   .. sourcecode:: http

      GET /user HTTP/1.1
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
        "email": test@example.com,
        "github_login": octocat,
        "pk": "458b04ed37ba4c9fa4ff712d9f99a651",
      }

   :reqheader Accept: the response content type depends on
                      :mailheader:`Accept` header
   :reqheader Authorization: OAuth token to authenticate

   :resheader Content-Type: this depends on :mailheader:`Accept`
                            header of request
   :statuscode 200: no error
