Projects
========

.. automodule:: api.v1.project
    :members:

.. code-block:: json

    {
      "project": {
        "analysis_priority": 0, 
        "analysis_requested_at": "Tue, 07 Oct 2014 12:30:20 GMT", 
        "analyze": true, 
        "checkignore": "*/site-packages/*\n*/dist-packages/*\n*/build/*\n*/eggs/*\n*/migrations/*\n*/alembic/versions/*\n", 
        "database_name": "checkmate_4b48b3caccfa4925b6d0148d50015cf2", 
        "github_data": {
          "created_at": "2012-02-27T09:33:29Z", 
          "default_branch": "master", 
          "description": "Web based translation tool with tight Git integration.", 
          "forks_count": 57, 
          "full_name": "nijel/weblate", 
          "id": 3559019, 
          "name": "weblate", 
          "open_issues_count": 50, 
          "owner": {
            "login": "nijel"
          }, 
          "private": false, 
          "size": 102011, 
          "stargazers_count": 180, 
          "url": "https://api.github.com/repos/nijel/weblate", 
          "watchers_count": 180
        }, 
        "last_analysis": {
          "dt": "Tue, 07 Oct 2014 12:30:17 GMT", 
          "status": "succeeded", 
          "task": {
            "__collection__": "task", 
            "pk": "50f7f7e1f12b4155b870582d04413a01"
          }
        }, 
        "name": "nijel/weblate", 
        "pk": "87f9cee084de483ba8bdcddc76934835", 
        "public": true, 
        "remotes": {
          "origin": {
            "branches": [
              "bootstrap", 
              "gh-pages", 
              "master"
            ], 
            "last_fetch": {
              "returncode": 0, 
              "stderr": "From https://github.com/nijel/weblate\n * [new branch]      bootstrap  -> origin/bootstrap\n * [new branch]      gh-pages   -> origin/gh-pages\n * [new branch]      master     -> origin/master\n", 
              "stdout": "From https://github.com/nijel/weblate\n * [new branch]      bootstrap  -> origin/bootstrap\n * [new branch]      gh-pages   -> origin/gh-pages\n * [new branch]      master     -> origin/master\n", 
              "time": "Tue, 07 Oct 2014 12:23:29 GMT"
            }, 
            "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDVyBJoTlDdfgfAsfIfo8+yxG7zjJ7UCvmb1ToY4Z/tngSydawdxHjBg6/0rgyHIrBe+9/YL/ttvcuDL7hxZ/M95Gfn0Uiuuh/bhiTAuStaC3pV7HB1pqnIKY0DiN/uQVMh/B0iyQ9HOLJHNU9v6I/KoDligmzunL91qhxPyG8ZfBGCvX5AmAxGssX9V24vRKno29nHEq5n6h3DAKZTTyoC+eaUqZMtQW1RPle1FnBO7L4DfoQHSFHIKfWTDAmmCinokxlUrs4W620tr/bc/oigNfy5RUmZmIaIrOI/F48d5Wfee9PnLH8Zhe8x5WzRnNEA8gP+LtciRRP/kFHH45wr 87f9cee084de483ba8bdcddc76934835\n", 
            "tracked_branches": [], 
            "url": "https://github.com/nijel/weblate.git"
          }
        }, 
        "stats": {
          "contributors": 168, 
          "diff": "9668a07ba09c429c9ba98080bcde11a9", 
          "issues_summary": {
            "": {
              "python": {
                "code_patterns": {
                  "AnalysisError": 8
                }, 
                "pyflakes": {
                  "ImportStarUsed": 2
                }, 
                "pylint": {
                  "C0103": 239, 
                  "C0111": 241, 
                  "C0301": 78, 
                  "C0302": 4, 
                  "C0330": 1, 
                  "E0601": 1, 
                  "E0602": 1, 
                  "E0611": 1, 
                  "E1002": 32, 
                  "E1101": 130, 
                  "E1103": 3, 
                  "F0401": 230, 
                  "I0011": 10, 
                  "I0020": 9, 
                  "I0021": 2, 
                  "R0201": 122, 
                  "R0901": 1, 
                  "R0902": 6, 
                  "R0903": 63, 
                  "R0904": 14, 
                  "R0911": 3, 
                  "R0913": 11, 
                  "R0914": 3, 
                  "R0921": 5, 
                  "R0922": 3, 
                  "W0101": 1, 
                  "W0142": 9, 
                  "W0201": 1, 
                  "W0212": 1, 
                  "W0223": 1, 
                  "W0232": 175, 
                  "W0401": 2, 
                  "W0511": 1, 
                  "W0612": 1, 
                  "W0613": 109, 
                  "W0622": 1, 
                  "W0703": 9, 
                  "W0704": 5
                }
              }
            }
          }, 
          "issues_trend": {
            "added": [], 
            "deleted": [], 
            "modified": []
          }, 
          "n_commits": 13852, 
          "snapshot": "424950c5d923d3769a8354917ae6d254e4499389", 
          "summary": {
            "python": {
              "format": {
                "average_number_of_characters": 8665.723320158102, 
                "average_number_of_lines": 195.56126482213438, 
                "number_of_files": 253, 
                "total_number_of_characters": 2192428, 
                "total_number_of_lines": 49477
              }, 
              "pyflakes": {
                "n_errors": 0
              }, 
              "pylint": {
                "average_global_note": -31.237319995145953, 
                "n_errors": 0, 
                "n_warnings": 0
              }
            }
          }
        }
      }
    }
