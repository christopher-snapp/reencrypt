REENCRYPT
==========

:Author: Christopher A. Snapp <snappca@gmail.com>
:Version: 18.06
:Copyright: GPLv3

**reencrypt** makes it convenient to re-encrypt GPG encrypted files in place.

.. contents ::

Synopsis
--------

**reencrypt** [**-hv**] [**--help**] [**-r** *recipients-file*] *file1 file2 file3...*

Description
-----------

**reencrypt** provides a secure method for reencrypting a list of files using the public keys provided via a csv file.

.. Note::

    The decrypted contents are never stored to disk and are simply held in memory until the encryption occurs.

Recipients File
~~~~~~~~~~~~~~~

You must provide at least one recipient to **reencrypt** via a comma-separated value (csv) file.

**Example File Format:**

.. code-block::

    user1@example.com,847CA452151F19D696C2B5B14DBF4BBA10B22696
    user2@example.com,785C39AA97FBE1EDC3D449C106E78C0B882B21F5
    user3@example.com,76ABAD5CC6F98854F4B96E29396218BA9F3A1554

Options
-------

**-f** *file*
      the file containing commands to be executed

**-h, --help**
      display this help and exit

**-v**
      display version information and exit


Examples
--------

**Re-Encrypting a single file**

.. code-block::

    reencrypt -r RECIPIENTS.csv file1.asc

**Re-Encrypting a list of files**

.. code-block::

    reencrypt -r RECIPIENTS.csv file1.asc file2.gpg file3.asc

**Re-Encrypting all *.asc files**

.. code-block::

    reencrypt -r RECIPIENTS.csv *.asc
