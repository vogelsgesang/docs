===========
Get started
===========

**1. Connect your repository**

    Sign up via `GitHub <https://quantifiedcode.com/app/signup>`_ or `email <https://quantifiedcode.com/app/signup?tab=email>`_ and add a git repository.

**2. Add an SSH key to your server**

    For security reasons, we only access your private repositories via a SSH key. The SSH key will be automatically provided, once you'll add a private repository to your account.

    On the following pages, you'll find short tutorials on how to add the SSH key to your git server:

    * `GitHub <https://help.github.com/articles/generating-ssh-keys/>`_
    * `BitBucket <https://confluence.atlassian.com/display/BITBUCKET/Add+an+SSH+key+to+an+account>`_
    * :ref:`Local git server <ssh-gitserver>`

**3. Configure your analysis**

    After your project is added, go to your project's settings and configure your analysis. To exclude certain files from the analysis, add a .checkignore file to your repo. Visit the :ref:`Configuration<configuration_index>` chapter to learn more.

**4. Add a commit hook**

    To analyze your repo automatically with each commit, add a :ref:`commit hook <config_commit_hooks>` to your git server/service.

**4. Publish your code quality badge

    Finally, don't forget to add your project's code quality :ref:`badge <config_code_quality_badge>` to your README.
