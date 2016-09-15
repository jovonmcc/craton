.. _cells:

======
Cells
======

Definition of cell

Create Cell
============
.. glossary::
    POST 
        /v1/cells

Create a new Cell

Normal response codes: OK(200)

Error response codes: invalid request(400), validation exception(405)

Request
-------

+------------+------+---------+-------------------------+
| Name       | In   | Type    | Description             |
+============+======+=========+=========================+
| region_name| boody| string  | Unique name of the cell |
+------------+------+---------+-------------------------+
| region_id  | body | integer | Unique ID of the reigion|
+------------+------+---------+-------------------------+
| project_id | body | integer | ID of the project       |
+------------+------+---------+-------------------------+

Required Header
^^^^^^^^^^^^^^^

    - Content-Type: application/json
    - X-Auth-Token
    - X-Auth-User
    - X-Auth-Project

**Example Create Cell** (TO-DO)

..literalinclude:: ../../doc/api_samples/cells/cells-create-req.json
   :language: javascript

Response
--------

+-----------+------+---------+-------------------------+
| Name      | In   | Type    | Description             |
+===========+======+=========+=========================+
| cell      | body | object  | - cell_id               |
|           |      |         | - cell_name             |
|           |      |         | - region_id             |
|           |      |         | - project_id            |
|           |      |         | - note                  |
|           |      |         | - data                  |
+-----------+------+---------+-------------------------+
| cell_id   | body | object  | Unique ID of the cell   |
+-----------+------+---------+-------------------------+
| cell_name | body | object  | Unique name of the cell |
+-----------+------+---------+-------------------------+
| region_id | body | object  | Unique ID of the region |
+-----------+------+---------+-------------------------+

**Example Create Cell** (TO-DO)

..literalinclude:: ../../doc/api_samples/cells/cells-create-resp.json
   :language: javascript

List Cells
==========

.. glossary::  
    GET 
        /v1/cells

Gets all Cells

Normal response codes: OK(200)

Error response codes: invalid request(400), cell not found(404), validation exception(405)

Default response: unexpected error

Request
--------

+-----------+-------+---------+--------------------------+
| Name      | In    | Type    | Description              |
+===========+=======+=========+==========================+
| cell      | query | string  | Name of the cell to get  |
+-----------+-------+---------+--------------------------+
| region    | query | string  | Name of the region to get|
+-----------+-------+---------+--------------------------+ 

Required Header
^^^^^^^^^^^^^^^

    - Content-Type: application/json
    - X-Auth-Token
    - X-Auth-User
    - X-Auth-Project

Response
--------

+------------+------+---------+-------------------------+
| Name       | In   | Type    | Description             |
+============+======+=========+=========================+
| cells      | body | array   | array cell objects      |
+------------+------+---------+-------------------------+
| cell__id   | body | integer | Unique ID of the cell   |
+------------+------+---------+-------------------------+
| cell_name  | body | string  | Unique name of the cell |
+------------+------+---------+-------------------------+
| region_id  | body | integer | Unique ID of the region |
+------------+------+---------+-------------------------+
| project_id | body | ineger  | ID of the project       |
+------------+------+---------+-------------------------+
| note       | body | string  | Note used for governance|
+------------+------+---------+-------------------------+
| data       | body | object  | User defined data       |
+------------+------+---------+-------------------------+

**Example List Cells** (TO-DO)

..literalinclude:: ../../doc/api_samples/cells/cells-list-resp.json
   :language: javascript 

**Example Unexpected Error** (TO-DO)

..literalinclude:: ../../doc/api_samples/errors/errors-unexpected-resp.json
   :language: javascript

Update Cells
============

.. glossary:: 
    PUT 
        /v1/cells/{cell_id}

Update an existing cell

Normal response codes: OK(200)

Error response codes: invalid request(400), cell not found(404), validation exception(405)

Request
-------

+------------+------+---------+-------------------------+
| Name       | In   | Type    | Description             |
+============+======+=========+=========================+
| cell__id   | body | integer | Unique ID of the cell   |
+------------+------+---------+-------------------------+
| cell_name  | body | string  | Unique name of the cell |
+------------+------+---------+-------------------------+
| region_id  | body | integer | Unique ID of the region |
+------------+------+---------+-------------------------+
| project_id | body | ineger  | ID of the project       |
+------------+------+---------+-------------------------+
| note       | body | string  | Note used for governance|
+------------+------+---------+-------------------------+
| data       | body | object  | User defined data       |
+------------+------+---------+-------------------------+
| cell_id    | path | integer | Unique ID of the cell   |
+------------+------+---------+-------------------------+

Required Header
^^^^^^^^^^^^^^^

    - Content-Type: application/json
    - X-Auth-Token
    - X-Auth-User
    - X-Auth-Project

**Example Update Cell** (TO-DO)

..literalinclude:: ../../doc/api_samples/cells/cells-update-req.json
   :language: javascript

Response
--------

+-----------+------+---------+--------------------------+
| Name      | In   | Type    | Description              |
+===========+======+=========+==========================+
| cell      | body | object  | - cell_id                |
|           |      |         | - cell_name              |
|           |      |         | - region_id              |
|           |      |         | - project_id             |
|           |      |         | - note                   |
|           |      |         | - data                   |
+-----------+------+---------+--------------------------+
| cell_id   | body | object  | Unique ID of the cell    |
+-----------+------+---------+--------------------------+
| cell_name | body | object  | Unique name of the cell  |
+-----------+------+---------+--------------------------+
| region_id | body | object  | Unique ID of the region  |
+-----------+------+---------+--------------------------+
| project_id| body | ineger  | ID of the project        |
+-----------+------+---------+--------------------------+
| note      | body | string  | Note used for governance |
+-----------+------+---------+--------------------------+
| data      | body | object  | User defined data        |
+-----------+------+---------+--------------------------+

**Example Update Cell**  (TO-DO)

..literalinclude:: ../../doc/api_samples/cells/cells-update-resp.json
   :language: javascript

Update Cell Data
==================

.. glossary::
    PUT 
        /v1/cells/{cell_id}/data

Update user defined data for the cell

Normal response codes: OK(200)

Error response codes: invalid request(400), cell not found(404), validation exception(405)

Request
-------

+--------+------+---------+-------------------------+
| Name   | In   | Type    | Description             |
+========+======+=========+=========================+
| key    | body | string  | Identifier              |
+--------+------+---------+-------------------------+
| value  | body | object  | Data                    |
+--------+------+---------+-------------------------+
| cell_id| path | integer | Unique ID of the project|
+--------+------+---------+-------------------------+

Required Header
^^^^^^^^^^^^^^^

    - Content-Type: Content_Type
    - X-Auth-Token: X-Auth-Token
    - X-Auth-User: X-Auth-User
    - X-Auth-Project: X-Auth-Project

**Example Update Cell Data** (TO-DO)

..literalinclude:: ../../doc/api_samples/cells/cells-upadate—data-req.json
   :language: javascript

Response
--------

.. rest_parameters:: parameters.yaml

    - key: key
    - value: value

**Example Update Cell Data** (TO-DO)

..literalinclude:: ../../doc/api_samples/cells/cells-update-data-resp.json
   :language: javascript

Delete Cell
===========

.. rest_method:: DELETE /v1/cells/{cell_id}

Deletes an existing record of a Cell

Normal response codes: OK(200)

Error response codes: invalid request(400), cell not found(404)

Request
-------

.. rest_parameters:: parameters.yaml

    - cell_id: cell_id

Required Header
^^^^^^^^^^^^^^^

    - Content-Type: Content_Type
    - X-Auth-Token: X-Auth-Token
    - X-Auth-User: X-Auth-User
    - X-Auth-Project: X-Auth-Project

Response
--------

No body content is returned on a successful DELETE

Delete Cell Data
================

.. rest_method:: DELETE /v1/cells/{cell_id}/data

Delete existing key/value data for the cell

Normal response codes: OK(200)

Error response codes: invalid request(400), cell not found(404) validation exception(405)

Request
-------

.. rest_parameters:: parameters.yaml

    - cell_id: cell_id

Required Header
^^^^^^^^^^^^^^^

    - Content-Type: Content_Type
    - X-Auth-Token: X-Auth-Token
    - X-Auth-User: X-Auth-User
    - X-Auth-Project: X-Auth-Project

Response
--------

No body content is returned on a successful DELETE
