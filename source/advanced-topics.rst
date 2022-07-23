Multithreading
==============


Restricting a job to run on specific CPUs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Suppose you have a job or a process that runs in parallel on multiple cores and you would like to limit the number of CPUs that this job has access to. The set of CPUs a process is eligible to run on is determined by the process's "CPU affinity mask".

Under Linux, a job or process's affinity can be set by executing the ``sched_setaffinity`` system call. There is a standard shell wrapper (i.e. a shell script that embeds a system command or utility, that saves a set of parameters passed to that command) that can be used to to set this called `taskset <https://linux.die.net/man/1/taskset>`_.

``taskset`` can be used to both start a job or process with a specific CPU affinity, as well as change the CPU affinity of an already-running job or process. Its syntax is as follows:

- To start a new job to run on specific CPUs:

    .. code:: bash

      taskset [options] mask command [argument...]

- To set the CPU affinity of a job with process id ``<pid>``:
  
    .. code:: bash

      taskset [options] -p [mask] <pid>

  By default, the mask is specified in hexadecimal. If you would instead like to use a numerical list of processors (from, say, ``0`` to ``N``), the ``-c`` (or ``--cpu-list``) flag can be used.

      
**Examples:**

#. To start a job with name <job> to run on specific CPUs:

    .. code:: bash

        taskset --cpu-list 0-2,4 <job>

    This will run  <job> on CPUs ``#0``, ``#1``, ``#2``, and ``#4``.

#. To retrieve the CPU affinity of a process whose process id (pid) is ``<pid>``

    .. code:: bash

        taskset --pid <pid>

    or in short-hand

    .. code:: bash

        taskset -p <pid>

#. To change the CPU affinity of a process whose process id is ``<pid>``

    .. code:: bash

        taskset --cpu-list --pid 0-3 <pid>

    or in shorthand

    .. code:: bash

        taskset -cp 0-3 <pid>

    which will set the job with process id ``<pid>`` to run on CPUs ``#0``, ``#1``, ``#2``, and ``#3``.

