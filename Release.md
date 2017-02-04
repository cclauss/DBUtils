Create a new DBUtils release:
=============================

* Check the documentation. If possible, update all translations.
  (Chinese translation was too old and has been removed for the time being.)

* Run all tests in DBUtils/Tests with Python version from 2.3 to 2.7.

* Check the examples in DBUtils/Examples with the current Webware version.

* Update and check the Release Notes and copyright information.

* Set version number and release date with `setversion.py`.

* Revert to old version number for translations that have not been updated.

* Build html pages using `buildhtml.py`.

* Create a tag in the SVN repository.

* Create a source tarball with:

        python setup.py sdist

  You will find the tarball in the "dist" folder.

  Under Windows, this will be a .zip file, otherwise a .tar.gz file.
  You can force .tar.gz under Windows with `--formats=gztar`,
  but you need to use Cygwin or have a tar binary installed.
  Generally, it is better to create the release under Unix to avoid
  problems with DOS linefeeds and missing file permission.

* Upload to the Python Package Index (PyPI, aka "cheese shop"):

    In your (Unix/Cygwin) home directory, create a .pypirc file as follows:

        echo "[server-login]
        username:myusername
        password:mypassword" > .pypirc

* Register the project with:

        python setup.py register

* Upload the source package with:

        python setup.py sdist upload

  You have to install setuptools to make this work.
  Alternatively, you can simply upload using the web interface.

  See also: http://www.python.org/~jeremy/weblog/030924.html

* Also, don't forget to update the Webware homepage:

  * http://www.w4py.org/DBUtils
  * http://www.w4py.org/DBUtils/Docs/
  * http://www.w4py.org/downloads/DBUtils/