.. Social Impact Network Documentation documentation master file, created by
   sphinx-quickstart on Mon Jan 18 17:17:55 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

===============================
Social Impact Token (SI Token)
===============================
.. warning:: Currently, only Social Impact Prototype Token (SIP Token) exists. See `SIP Token <https://github.com/Social-Impact-Network/Frontend>`_

The Social Impact Token (SI Token) is used for payment flows (including investment, allocation, interest and payouts).
SI Token is an ERC20 token on the Ethereum Blockchain, programmed in Solidity.
All interactions with SI Token can be done through `SI platform (frontend) <https://github.com/Social-Impact-Network/Frontend>`_.
Since the token was implemented according to the ERC20 standard, the basic functions (e.g. sending and receiving) can also be performed via any ERC20-enabled wallet.

Social Impact Prototype Token (SIP Token)
--------------------------------------------
Social Impact Network is currently in the prototype phase. In order to test the Social Impact Network and its Transparent Impact Measurement System <https://github.com/Social-Impact-Network/Frontend>`_, the Social Impact Prototype Token has been developed.

In contrast to SI Token, some simplified conditions were created for SIP Token. These conditions were created in order to reduce the regulatory aspects of the security token to a minimum.


Simplified conditions
~~~~~~~~~~~~~~~~~~~~~~~~
#. The underlying security is not publicly offered.
#. Investors and project beneficiaries are known to each other and limited. 
#. The aid organization and the beneficiary are identical and will be a natural person within UNDP Lebanon.
#. Proceeds from token sales will be received directly through the Smart Contract in ETH or DAI. No external financial service provider will be involved.
#. The token value is pegged at $1 (1 SIP = $1). There will be no calculation of `Asset Net value <https://github.com/Social-Impact-Network/Frontend>`_.
#. It is a single project funding and no other projects will be funded through this token.
#. The project duration of the project is limited to 6 months.
#. Interest and principal payments are made monthly.  
#. The interest and payouts will be credited to the investors' tokens and it is necessary to arrange the payment through the platform.



Investment and payout process (SIP Token)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. image:: http://www.plantuml.com/plantuml/png/PO-zJiGm3CVtF8Kbtg9TxevREY1L575pQDoh8N6Auvoeb8Sdj4C7Dkl_OVzyIcf5S_2cTFp0f56AsJJJx4A2wxa3dINc-mn31xstEaK9hIbFPrRwpdYRIR4CmOh2SsGLEsenpT3ry1Q_a25G3VAzDStDqjy4Ijx38l4JHuKfiqDN5rwGSQBHobhhhpWYFN03gCrBNXDOTa1S0MjxYDuAzE_LUuciirzXeXzqiDWrPasj-OzqfQH27tbZE7B7xyVLtMrDrHTpGdOv-5y0
    :alt: SIP token payment process


.. note:: SIP token is a payout token. Monthly interest and dividend payments are transferred to investors in DAI via token. Withdrawals can be initiated at any time via SI platform.

#. The (known) investors invests via the `SI platform (frontend) <https://github.com/Social-Impact-Network/Frontend>`_ and pays in DAI or Ether.
#. SIP tokens are generated (minted) by the smart contract and transferred to investor.
#. The investor's funds then are transferred (along with the funds of the other known investors) to the project beneficiary.
#. The project beneficiary, together with a contractor, builds a solar system for himself.
#. The beneficiary pays monthly interest and payouts directly to the smart contract in DAI.
#. DAI is credited to investors on proportional basis.
#. Investors can withdraw their credited DAI at any time.



Smart Contract
~~~~~~~~~~~~~~

The basic functionalities of the SIP's smart contract are the same as those of the SIP token.
Due to the mentioned simplification, the methods for calculating the NetAssetValue have been removed.
Due to the simplification, the SIP token is limited to a single project .
Due to the removal of the fiat payment channels, however, two methods for additional payment processes needed to be included in the smart contract:

.. list-table:: xxxx
   :widths: 50 50
   :header-rows: 1

   * - Method
     - Description
   * - Buy
     - Through the buy method, the known investor can buy the SIP tokens using Ether or Dai. This functionality is represented in the SI token through a licensed financial partner and preceding KYC processes.
   * - Claim (Beneficary)
     - The beneficiary is able to withdraw investors' DAI, which will be used to pay for the solar panel installation
     
Vision Social Impact Token 
----------------------------
.. image:: http://www.plantuml.com/plantuml/png/ZOsnJiCm48RtUueRoz21i6L0JOjQPQ58UOB3EIeJvwuwsqM0U7S2OGXgL7MozNsV_bl5H9Po7o1sNevar6EEx2WoViAQN7SmpT9kDAZX0rdNCEsCMM2jrh9DHA34EwDtgCpqRHJxu4yCbKjgq_uv3CiZtggaH-ePDvhDim5y0ImQTPu2rlsHNC9jblO6AUBYvUS7KDPoufZKyBR4vVB-JqnuCUKu4V9VZEylAYlVujuE9Fw3abSPnY_xuSZbG4gOMnthfiOdqrTsQK3NTSLSLvntTtETd7TImegbpNtu1W00
    :alt: SI Fund Vision

The basic concept of the SI Network Funding mechanism is that the investor invests in a funding pool. For his investment in this pool, the investor receives SI Tokens according to the token price and the investment amount.
The token price is calculated according to the `Asset Net Value <https://github.com/Social-Impact-Network/Frontend>`_ and reflects the real performance of the projects.
The funds of the funding pool are used by the authorized aid organizations to implement planned sustainable projects with a defined ROI (on average >6%).
All SI projects generate revenue and distribute them to investors.
A list of planned projects can be viewed on the `SI platform (front end) <https://github.com/Social-Impact-Network/Frontend>`_.
Dividends from the investment projects are distributed to the investors in DAI or Fiat (e.g. Eur, USD) at regular intervals (usually monthly).


Investment and payout process (SI Token)
------------------------------------------------


.. image:: http://www.plantuml.com/plantuml/png/PP11Jy9048Nl-oicyQA9lu1U0F70oOQANBmCssqxqixYT5QofZ_U0OmXyTRCU-_hUpiV5KNJqBjfpLzXr2YJkzpSx7eOOLkj7k5vku4eu2Lh1EqafhPxPsY8aJrX3qVBS92pgLf3sQCsKOR2JNSBLlfCOTUHXgaQp0TFaLNGw-HcrRg4rtW830EPaTl2pNP8vozGwWqiyIDuXIPn7Me3BgY65scHwHkL8Xja4tmWQtinZKPOfZm2SWt4jiOeLUnHe7oppYVI3lnlWoX6N0OE3NcKVCFwYnYkn7pk8rUfXj1R8o5FcWruly_G6a9GJJkSkeV2_H-wej4Y-tHPTiGSaux5pRFV_Fcg5ixkHpSFNAUX_m40
    :alt: SI Token process

.. warning:: To learn about the Social Impact Prototype Token (SIP Token) investment and payout process, please click `here <https://github.com/Social-Impact-Network/Frontend>`_.

.. note:: SI token is a payout token. Monthly interest and dividend payments are transferred to investors in DAI via token. Withdrawals can be initiated at any time via SI platform.

.. warning:: Currently, SI Network only funds solar projects


#. Investor purchases SI tokens through a licensed partner or through SI platform.
#. SI tokens are created (minted) for the investor and sent to him.
#. Investor's funds (along with other investors' funds) are sent to aid organization.
#. Aid organization and contractor, together with a cotractor, build a solar system for a specified beneficiary.
#. Beneficiary pays the received energy to the aid organization.
#. Aid organization exchanges the payment in Dai through an exchange.
#. DAI goes directly into the smart contract.
#. DAI is distributed proportionately to all investors; portions of payments are kept (reinvested) for future projects.
