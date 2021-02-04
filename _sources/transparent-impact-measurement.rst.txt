==============================================
Transparent Impact Measurement System (TIM)
==============================================

.. warning:: Currently, SI Network only funds solar projects, therefore Impact Measurment System only stores data from solar projects

Transparent Impact Measurement (TIM) ensures that the funded social impact projects can be examined for the expected social impact. At the same time, impact measurement makes it possible to keep track of the performance of the investment. Through impact measurements, the investor can understand even minor discrepancies between the expected impact and the achieved impact. This information enables the review of the social impact of the investment for third parties. At the same time this information can be used for trading and investment decisions. Impact values also include the financial performance of individual projects and are tracked in real time.
Impact values of all projects are publicly available.

Impact Values
-----------------
Impact values are all data that can be used to assess direct positive environmental and social benefits (e.g., clean electricity generation in kWh). In addition, impact values are also financial indicators that can be used to assess the financial performance of funded SI Network projects (e.g. APY).

The following impact data is collected for all Social Impact Network projects:

.. list-table:: General Impact Values for all SI projects
   :widths: 50 50
   :header-rows: 1

 

   * - Value
     - Description
   * - Project description
     - A general description of the project, description of the implementing aid organization, beneficiary and social impact.
   * - News
     - Current news (e.g. installation status, payouts) of the project.
   * - Location
     - Location of the project implementation
   * - Project cost
     - The total cost of the project
   * - APY
     - Average annual APY over the lifetime of the project.

Additionally, the following impact values are stored for solar projects:

.. list-table:: Solar Impact Values
   :widths: 50 50
   :header-rows: 1

   * - Value
     - Description
   * - Expected duration of the solar installation
     - Duration of the whole project
   * - Estimated energy generated per year
     - Amount of kwh generated on average per year by the project.
   * - Avoided CO2
     - Amount of CO2 (in KG) saved by the project over the entire project lifetime.
   * - System power
     - The maximum power of the solar system in kwp


Storage of Impact Values
----------------------------

SI Impact values are stored in a decentralized, publicly accessible database (BigChainDB). Anyone can operate SI nodes and thus obtain a complete image of all impact values. More independent SI Nodes participate in Social Impact Network, provide higher resistance against tampering SI impact values. By running an independent SI Node, the database becomes decentralized and protected from tampering. If you want to support SI network and protect impact values `create your own SI node <#id7>`_ . BigChainDB is used to store impact values. 
Querying impact values is performed through BigchainDB nodes (SI nodes). For a full explanation of BigChainDB and how it interacts with nodes, see `full BigchainDB documentation <https://docs.bigchaindb.com/en/latest/index.html>`_.

Main REST API URLs
~~~~~~~~~~~~~~~~~~~~

Core Social Impact Network Team operate an SI node at http://3.121.239.82:9984/. Impact values can be retrieved directly via this SI node or via other `active nodes <#list-of-active-si-nodesd>`_ Main REST API URLs for retrieving impact values (JSON) via this SI node: 

.. list-table:: Main API URLs
   :widths: 50 50
   :header-rows: 1

   * - Description
     - URL
   * - list of all projects with associated Asset IDs
     - http://3.121.239.82:9984/api/v1/transactions?asset_id=ed9dde99816fb0e378e7e67ad035555ee37f5c1b8976906af6363022aafb2f74&last_tx=true
   * - General Project data (impact values)
     - http://3.121.239.82:9984/api/v1/transactions?asset_id= [Project Asset ID]
   * - Current KwH data and news
     - http://3.121.239.82:9984/api/v1/transactions?asset_id= [Project Asset ID] &last_tx=true

List of all projects with associated Asset ID
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A list of all SI projects can be found via Asset ID ``ed9dde99816fb0e378e7e67ad035555ee37f5c1b8976906af6363022aafb2f74``: http://3.121.239.82:9984/api/v1/transactions?asset_id=ed9dde99816fb0e378e7e67ad035555ee37f5c1b8976906af6363022aafb2f74&last_tx=true.
Each project is located with its associated Asset ID in the JSON object as an array. You will find the asset IDs of all projects set up by SI network in entry ``array[1].metadata.projects``.
Asset ID is the identifier of a project. When a project is created via a CREATE transaction, this unique Asset ID is assigned and cannot be changed.  The Asset ID can thus be considered equivalent to a unique Project ID. The list of all project asset IDs thus provides a list of unique project IDs. These project IDs can be used to uniquely identify the project.

Initialization of a project list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To initialize a new project list, use  `create_project_list.js <https://github.com/Social-Impact-Network/Frontend/blob/master/bigchain-interaction-scripts/create_project_list.js>`_.

Project data
~~~~~~~~~~~~
Project data can be retrieved via Asset ID. This is done by accessing the ``CREATE`` transaction that created the project.
Project data (e.g. description, duration) cannot be changed subsequently.
Updates to the projects can only be submitted via the news function.
To retrieve, for example, the project data of the project with asset ID ``b2893734f1ab5533086d74cb0055ee285b58f94fa6f90695d69605b72b6361cd`` via SI node of 
Social Impact Network, the following link can be used: http://3.121.239.82:9984/api/v1/transactions?asset_id=b2893734f1ab5533086d74cb0055ee285b58f94fa6f90695d69605b72b6361cd.
Within the JSON Object, Project data can be found at ``array[0].asset.data``.

Initialization of a new project
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To create a new project, use the script `create_new_project.js <https://github.com/Social-Impact-Network/Frontend/blob/master/bigchain-interaction-scripts/create_new_project.js>`_

View Solar impact values and news
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To view specific impact values for solar projects, the last ``UPDATE`` transaction of an Asset ID is called. This can be done by adding parameter ``&last_tx=true`` to project data URL.
From this transaction it is possible to read how much solar power was generated by the solar project (generated khw), statistical solar data , as well as news regarding the project (e.g. implementation status). 

To retrieve, for example, the impact values and news of the project with asset ID ``b2893734f1ab5533086d74cb0055ee285b58f94fa6f90695d69605b72b6361cd`` via SI node of the
Social Impact Network, the following link can be used: http://3.121.239.82:9984/api/v1/transactions?asset_id=b2893734f1ab5533086d74cb0055ee285b58f94fa6f90695d69605b72b6361cd&last_tx=true .
Within the JSON Object, the impact values and news can be found at ``array[0].metadata``.

Insert Solar Impact Values
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To add new Solar Impact values to a project, the  `Inverter BigchainDB Bridge repo <https://github.com/Social-Impact-Network/Inverter-BigchainDB-Bridge>`_ can be used.
Please review ``README.md`` before usage.

Social Impact Nodes
--------------------
SI Nodes enable authentic storage of impact values through decentralized storage.


Create your own SI Node
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. note:: In the current prototype phase, external nodes cannot be added. If you would like to be notified as soon as you can set up your own node, please send us an email with subject "Set up node" to `EMAIL <https://github.com/Social-Impact-Network/Frontend>`_. 

Setting up your own node supports the security of the impact values and helps the overall social impact network.
To set up your own network, please follow the description in the `BigChainDB documentation <http://docs.bigchaindb.com/projects/server/en/latest/production-nodes/index.html>`_.


List of active SI Nodes
~~~~~~~~~~~~~~~~~~~~~~~~~

Here you find a non-exhaustive list of active nodes.
If you want your SI node to be added to this list, please send us an email to `Email <mailto:felix.maduakor@mlcrypt.de>`__.

.. list-table:: List of Known SI Nodes
   :widths: 25 25 25 25
   :header-rows: 1

   * - Type
     - Owner
     - Link
     - Status
   * - Coordinator Node
     - Social Impact Network
     - http://3.121.239.82:9984/api/v1/
     - Active
   * - Node
     - Social Impact Network
     - http://3.121.239.82:9984/api/v1/
     - Active
