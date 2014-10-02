Users
=====

.. http:post:: /login

    Simple POST Resource to login a User.

    **Example response**:

    .. sourcecode:: http

      {
        "access_token" : access_token.token,
        "message" : "Success!"
      },

    :reqheader Accept: the response content type depends on
                      :mailheader:`Accept` header
    :resheader Content-Type: this depends on :mailheader:`Accept`
                            header of request
    :statuscode 200: no error
    :statuscode 403: other error
    :statuscode 404: unknown user
   
.. http:post:: /logout

    Logs out the current authorized User.

    **Example response**:

    .. sourcecode:: http

      {
        "message": "success",
      }

    :reqheader Accept: the response content type depends on
                      :mailheader:`Accept` header
    :reqheader Authorization: OAuth token to authenticate

    :resheader Content-Type: this depends on :mailheader:`Accept`
                            header of request
    :statuscode 200: no error

.. http:get:: /user

    Returns information for a User Document. (Email, connected Accounts, etc.)

    **Example response**:

    .. sourcecode:: http

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

.. http:post:: /signup

    Signup POST Resource. Fails if the User already exists. (if the email is already in use)
    Also fails if a form contains errors and returns these `errorss`.

    **Example response**:

    .. sourcecode:: http

      {
        "message" : "Success!"
      },

    :reqheader Accept: the response content type depends on
                      :mailheader:`Accept` header
    :resheader Content-Type: this depends on :mailheader:`Accept`
                            header of request
    :statuscode 200: no error
    :statuscode 403: other error
