MuG Coding Guidelines
=====================

The purpose of this document is to provide a description of the standards that 
code should conform to so that everything can be share and developed with ease.

Versions
--------

- Python 2.7
- Python 3.5

Style
-----

This should follow the PEP8 standard defined by the
`Python community <https://www.python.org/dev/peps/pep-0008/>`_. Also check out
the
`Google Python Style Guide <https://google.github.io/styleguide/pyguide.html>`_,
a quick and easy reference.

This should be enforced with the use of `pylint <https://www.pylint.org/>`_ to
ensure that we are matching the PEP8 coding standard.

In addition for every script that is written at the top of ALL python
scripts/modules should be the stub license agreement


Documentation
-------------

For this we use ReadTheDocs. This is based on the Sphinx annotation servers and
the reStructuredText format (
`Primer <http://www.sphinx-doc.org/en/stable/rest.html>`_ and
`RTD related docs <http://documentation-style-guide-sphinx.readthedocs.io/en/latest/style-guide.html>`_)


Pipelines
---------

All functions should have matching documentation describing the purpose of the
function, the inputs, outputs and where relevant an example piece of code
showing how to call the function:

.. code-block:: python
   :linenos:

   """
   Assembly Index Manager

   Manges the creation of indexes for a given genome assembly file. If the
   downloaded file has not been unzipped then it will get unzipped here.
   There are then 3 indexers that are available including BWA, Bowtie2 and
   GEM. If the indexes already exist for the given file then the indexing
   is not rerun.

   Parameters
   ----------
   file_name : str
      Location of the assembly FASTA file

   Returns
   -------
   dict
      bowtie : str
         Location of the Bowtie index file
      bwa : str
         Location of the BWA index file
      gem : str
         Location of the gem index file

   Example
   -------
   .. code-block:: python
     :linenos:
     
     from tool.common import common
     cf = common()
     
     indexes = cf.run_indexers('/<data_dir>/human_GRCh38.fa.gz')
     print(indexes)
     

   """


Architectural Design Record (ADR)
---------------------------------

For all repositories there should be a document called adr.rst. This should
record choices that have been mande and summaries the reason for those
decisions. This is to provide an in-code record of the design process and
reasoning behind why technologies have been selected. In the case of python,
pytest, pyenv and pyenv-virtualenv this is the standard setup for use within the
pyCOMPSs environment. It is the selection of the key technology that is
important for the most part, but there will be times that one technology was
chosen over another due to the libraries that are used.


Testing
-------

pytest is the standard in the Python community and has been adopted for testing
within the MuG WP4 related code.

As with all python scripts these should have the licence stub and documentation
for all functions.

Runs of tests should also tidy up after themselves once they have completed so
that the environment is clean ready for the next test case to run. This could
mean that some files will get generated multiple times, but these should be
smalls sample datasets.


Sample Data
^^^^^^^^^^^

For all test cases there should be matching datasets that are packaged within
the repo.

All datasets should be in the directory `<repo>/tests/data` with a name patching
the pattern <script_name>.<species>.<assembly>.fasta for genome files and
<script_name>.<accession>.fastq for read files.

Only the raw files should be stored. For testing these should be small files
(~100kB).