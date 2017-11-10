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

HOWTO - Configuration Files
===========================

There are 2

config.json
^^^^^^^^^^^

Defines the configurations required for by the pipeline including parameters that need to be passed from the VRE submission form, file and the related metadata as well as the output files that need to be produced by the pipeline.

.. code-block:: none
   :linenos:

   {
       "input_files": [
           {
               "required": true,
               "allow_multiple": false,
               "name": "genome",
               "value": "<unique_file_id>"
           }
       ],
       "arguments": [
           {
               "name": "project",
               "value": "run001"
           },
           {
               "name": "description",
               "value": null
           }
       ],
       "output_files": [
           {
               "required": true,
               "allow_multiple": false,
               "name": "bwa_index",
               "file": {
                   "file_type": "TAR",
                   "meta_data": {
                       "visible": true,
                       "tool": "bwq_indexer",
                       "description": "Output"
                   },
                   "file_path": "tests/data/macs2.Human.GCA_000001405.22.fasta.bwa.tar.gz",
                   "data_type": "sequence_mapping_index_bwa",
                   "compressed": "gzip"
               }
           }
       ]
   }


input_file_metadata.json
^^^^^^^^^^^^^^^^^^^^^^^^

Lists the file location that are used as input. The configuration names should match those that are in the config.json file defined above.

.. code-block:: none
   :linenos:

   [
       {
           "_id": "<unique_file_id>",
           "data_type": "sequence_dna",
           "file_type": "FASTA",
           "file_path": "tests/data/macs2.Human.GCA_000001405.22.fasta",
           "compressed": 0,
           "sources": [],
           "creation_time": {
               "sec": 1503567524,
               "usec": 0
           },
           "taxon_id": "0",
           "meta_data": {
               "visible": true,
               "validated": 1,
               "assembly": "GCA_000001405.22"
           }
       }
   ]