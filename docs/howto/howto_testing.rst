.. See the NOTICE file distributed with this work for additional information
   regarding copyright ownership.

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.

HOWTO - Testing Your Code
=========================

Running the Code
----------------
To run the code it needs a config.json file and an input_metadata.json file to provide the input.

Running the pipeline manually
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: none
   :linenos:

   python process_test.py --config config.json --in_metadata input_files.json --out_metadata output_metadata.json


Testing a Tools and Pipelines
-----------------------------

As defined in the coding standards documentation, it is


Automated Testing
-----------------

Once you have defined your test functions it is handle to then hook up the repository with an automated testing framework that can notify you if there are unexpected changes to the behaviour of your code. This is often triggered whenever there is a push to the repository.


Running in COMPSs
-----------------

