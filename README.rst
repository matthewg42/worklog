NAME
----

worklog - work logging / diary system


SYNOPSIS
--------

.. code:: shell

    worklog [options] [message]


DESCRIPTION
-----------


*worklog* finds a ``.worklog`` file in the current working directory or, failing that, looks up the directory structure until it finds one. When it does find one, that is considered to be the root of the current project (something like ``.git`` directories).

The ``.worklog`` file is used to provide settings for the current project. This includes a ``LOG_DIR`` path, which specifies the location of log files relative to the ``.worklog`` file.

When *worklog* is invoked, it finds out the ``LOG_DIR``, and, if necessary creates a log file for today's date inside ``LOG_DIR``. The directory has structure as follows:

.. code:: shell

    LOG_DIR/
    LOG_DIR/YYYY-MM/
    LOG_DIR/YYYY-MM/YYYY-MM-DD

Log files have a dated entry made and then EDITOR (or vi/vim) is invoked to edit the file.

OPTIONS
-------

.. list-table:: 
   :widths: 8 12 80
   :header-rows: 1

   * - Option
     - Parameters
     - Description
   * - -1
     - 
     - Add a one-line quick message into the log - does not put blank lines 
       before or after the entry.
   * - -a  
     - 
     - Amend existing entry rather than adding a new entry timestamp and padding
   * - -d
     - *level*
     - Print diagnostic messages while executing. The value of *level* must be 
       an integer. The higher the number, the more verbose the diagnostic output 
       will be.
   * - -e  
     - 
     - After an entry has been made, echo the latest file to stdout.
   * - --help, -h
     - 
     - Show usage and exit
   * - -i
     - 
     - Create a ``.worklog`` file in the current working directory
   * - -I
     - 
     - Print the path to the current ``.worklog`` file, and then print the
       contents of the file.
   * - -l 
     - *logdir*
     - Specify the path to thew log directory, relative to the .worklog file. 
       This over-rides the value in the .worklog.  If used with the -i option, 
       this must come before it in the command line options, else it will be 
       ignored.
   * - -r  
     - 
     - Read the most recently edited log file. If a single parameter is 
       provided, it is is interpretted as a number of days, and all files 
       modified in the last that many days will be read.
   * - -s  
     - *subject*
     - Set the subject. The default value is taken from the DEFAULT_SUBJECT
       value in the ``.worklog`` file, or is "general" if not defined there.
   * - -S
     - 
     - List subjects for current worklog and exit. The default subject is
       indicated with the text "[default]" to the right of the subject name.
   * - --version, -v
     - 
     - Print the program description and version.
   * - -w
     - *path*
     - Instead of searching for the ``.worklog`` file, use *path*.

ENVIRONMENT
-----------

.. list-table:: 
   :widths: 10 90
   :header-rows: 1

   * - Variable
     - Description
   * - DBLEV_S
     - Set debugging level for script (over-ride with -D option).
   * - PAGER
     - The program used to view log entries with the -r option.
   * - EDITOR
     - The program used to edit entries.

LICENSE
-------

**worklog** is released under the GNU GPL (version 3, 29 June 2007). A copy
of the license should have been provided in the distribution of the
software in a file called "LICENSE.GPL". If you can't find this, then
try here: http://www.gnu.org/copyleft/gpl.html

AUTHOR
------

Mouse http://orthogonal-systems.co.uk/

CHANGELOG
---------

Date:2017-06-03 Created, Author MNG
    Original version.

BUGS
----

Please report bugs to the author.

SEE ALSO
--------
