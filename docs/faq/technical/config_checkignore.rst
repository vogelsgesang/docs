================================================
Can I exclude files / folders from the analysis?
================================================

Yes. Just add a **.checkignore** file to the root folder of your repo. The syntax of **.checkignore** files is identical with the syntax of `.gitignore's <http://git-scm.com/docs/gitignore`_. files. Files and folders that are mentioned in the **.checkignore** won't be analyzed anymore, when you project is re-analyzed.

The following example excludes all files and folders that are in the “test” folder. In addition, the file “demo.py” is not analyzed.

.. code-block:: python
  # .checkignore example
  # Exclude all test folders
  **/test
  # Exclude demo.py files
  demo.py

