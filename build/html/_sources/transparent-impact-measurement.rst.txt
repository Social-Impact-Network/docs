==============================================
Transparent Impact Measurement System (TIM)
==============================================

.. warning:: Currently, SI Network only funds solar projects, therefore the Impact Measurment System only stores data from solar projects

Transparent Impact Measurement (TIM) ensures that the funded social impact projects can be examined for the expected social impact. At the same time, impact measurement makes it possible to keep track of the performance of the investment. Through impact measurements, the investor can understand even minor discrepancies between the expected impact and the achieved impact. This information enables the review of the social impact of the investment for third parties and at the same time this information can be used for trading and investment decisions. Impact values also include the financial performance of individual projects and are tracked in real time.
Impact values of all projects are publicly available.

Impact Values
-----------------
Impact values are all any data that can be used to assess direct positive environmental and social benefits (e.g., clean electricity generation in kWh). In addition, impact values are also financial indicators that can be used to assess the financial performance of funded SI Network projects (e.g. APY).

The following impact data is collected for all Social Impact Network projects:

.. list-table:: Impact Werte für alle Social Impact Projekte
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

SI Impact values are stored in a decentralized, publicly accessible database (BigChainDB). Everyone can operate an SI node and thus obtain a complete image of all impact values. The more independent SI Nodes participate in the Social Impact network, the more resistant against tampering the impact values are. By running an independent SI Node, the database becomes decentralized and protected from tampering. If you want to support SI network and protect impact values `create your own SI node <https://github.com/Social-Impact-Network/Frontend>`_ . A BigChainDB is used to store impact values. 
Querying impact values is performed through BigchainDB nodes (SI nodes). For a full explanation of BigChainDB and how it interacts with nodes, see `BigchainDB documentation <https://github.com/Social-Impact-Network/Frontend>`_.

Main REST API URLs
~~~~~~~~~~~~~~~~~~~~

Core Social Impact Network Team operate an SI node at `HERE URL <https://github.com/Social-Impact-Network/Frontend>`_. Impact values can be retrieved directly via this SI node or via other `active nodes <https://github.com/Social-Impact-Network/Frontend>`_ Main REST API URLs for retrieving impact values (JSON) via this SI node: 

.. list-table:: Main API URLs
   :widths: 50 50
   :header-rows: 1

   * - Description
     - URL
   * - list of all projects with associated Asset IDs
     - `HERE URL <https://github.com/Social-Impact-Network/Frontend>`_
   * - General Project data (impact values)
     - `HERE URL <https://github.com/Social-Impact-Network/Frontend>`_
   * - Current KwH data and news
     - `HERE URL <https://github.com/Social-Impact-Network/Frontend>`_


List of all projects with associated Asset ID
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A list of all projects can be found under the following link: `HERE URL <https://github.com/Social-Impact-Network/Frontend>`_ Each project is located with its associated asset ID in the JSON object as an array. You will find the asset IDs of all projects set up by the SI network in entry `Metadata <https://github.com/Social-Impact-Network/Frontend>`_.
Asset ID is the identifier of a project. When a project is created via a CREATE transaction, this unique Asset ID is assigned and cannot be changed.  The Asset ID can thus be considered equivalent to a unique Project ID. The list of all project asset IDs thus provides a list of unique project IDs. These project IDs can be used to uniquely identify the project.

Initialization of a project list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To initialize a new project list, use  `create_project_list.js <https://github.com/Social-Impact-Network/Frontend>`_.

Project data
~~~~~~~~~~~~
Project data can be retrieved via the AssetID. This is done by accessing the CREATE transaction that created the project.
Project data (e.g. description, duration) cannot be changed subsequently.
Updates to the projects can only be submitted via the news function.
The following link is used for this purpose: `URL <https://github.com/Social-Impact-Network/Frontend>`_.
To retrieve, for example, the project data of the project with asset ID `ASSET <https://github.com/Social-Impact-Network/Frontend>`_ via SI node of the
Social Impact Network, the following link can be used: `URL <https://github.com/Social-Impact-Network/Frontend>`_.
Within the JSON Object, Project data can be found at `asset, data <https://github.com/Social-Impact-Network/Frontend>`_.

Initialization of a new project
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To create a new project, use the script `create_new_project.js <https://github.com/Social-Impact-Network/Frontend>`_

View Solar impact values and news
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To vie specific impact values for solar projects, the last UPDATE transaction of an `Asset ID <https://github.com/Social-Impact-Network/Frontend>`_is called. 
From this transaction it is possible to read how much solar power was generated by the solar project (generated khw), as well as other statistical solar data.
At the same time, the `events.news <https://github.com/Social-Impact-Network/Frontend>`_ entry contains the current and past news about the project.
To retrieve the latest entry in the database through the SI node of the Social Impact Network, the following link can be used: `URL <https://github.com/Social-Impact-Network/Frontend>`_.

Insert Solar Impact Values
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To add new Solar Impact values to a project, the following script `push_impact_measurement.js <https://github.com/Social-Impact-Network/Frontend>`_ can be used.
For solar systems with SunnyPortal inverters, the following project `SPMonitorBridge <https://github.com/Social-Impact-Network/Frontend>`_ can be used


Social Impact Nodes
--------------------
SI Nodes enable authentic storage of impact values through decentralized storage.


Create your own SI Node
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. note:: In the current prototype phase, external nodes cannot be added. If you would like to be notified as soon as you can set up your own node, please send us an email with subject "Set up node" to `EMAIL <https://github.com/Social-Impact-Network/Frontend>`_. 

Setting up your own node supports the security of the impact values and helps the overall social impact network.
To set up your own network, please follow the description in the BigchainDB documentation `URL <https://github.com/Social-Impact-Network/Frontend>`_.


List of active SI Nodes
~~~~~~~~~~~~~~~~~~~~~~~~~

Here you find a non-exhaustive list of active nodes.
If you want your SI node to be added to this list, please send us an email to `Email <https://github.com/Social-Impact-Network/Frontend>`_.

.. list-table:: List of Known SI Nodes
   :widths: 25 25 25 25
   :header-rows: 1

   * - Type
     - Owner
     - Link
     - Status
   * - Coordinator Node
     - Social Impact Network
     - `HIER URL <https://github.com/Social-Impact-Network/Frontend>`_
     - Active
   * - Node
     - Social Impact Network
     - `HIER URL <https://github.com/Social-Impact-Network/Frontend>`_
     - Active
