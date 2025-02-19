=========================
stock_location_orderpoint
=========================

.. 
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
   !! This file is generated by oca-gen-addon-readme !!
   !! changes will be overwritten.                   !!
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
   !! source digest: sha256:81ef0ccff7368de6a1cc344470b60a7a9dfbacc8f077d2999fa0690bb20e2dd6
   !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

.. |badge1| image:: https://img.shields.io/badge/maturity-Beta-yellow.png
    :target: https://odoo-community.org/page/development-status
    :alt: Beta
.. |badge2| image:: https://img.shields.io/badge/licence-AGPL--3-blue.png
    :target: http://www.gnu.org/licenses/agpl-3.0-standalone.html
    :alt: License: AGPL-3
.. |badge3| image:: https://img.shields.io/badge/github-OCA%2Fstock--logistics--orderpoint-lightgray.png?logo=github
    :target: https://github.com/OCA/stock-logistics-orderpoint/tree/16.0/stock_location_orderpoint
    :alt: OCA/stock-logistics-orderpoint
.. |badge4| image:: https://img.shields.io/badge/weblate-Translate%20me-F47D42.png
    :target: https://translation.odoo-community.org/projects/stock-logistics-orderpoint-16-0/stock-logistics-orderpoint-16-0-stock_location_orderpoint
    :alt: Translate me on Weblate
.. |badge5| image:: https://img.shields.io/badge/runboat-Try%20me-875A7B.png
    :target: https://runboat.odoo-community.org/builds?repo=OCA/stock-logistics-orderpoint&target_branch=16.0
    :alt: Try me on Runboat

|badge1| |badge2| |badge3| |badge4| |badge5|

Declare orderpoint on a location allowing to replenish any product with the same criteria.
This is for an internal warehouse replenishment currently not compatible with the purchase buy route.

**Table of contents**

.. contents::
   :local:

Configuration
=============

First configuration
===================

#. In order to replenish your stock location from another one, you first need
   to set the multi locations configuration.
#. So, go to Inventory > Configuration > Settings > Warehouse
#. Check the 'Storage Locations' box.
#. As you should be able to configure a dedicated route to replenishment, you
   should also activate, in the same menu, the 'Multi-Step Routes' box.

Locations configuration
=======================

#. Identify the location you want to apply a replenishment rule (e.g.: WH/Stock)
#. Create (if not exists) a new location for replenishment under Warehouse view (e.g.: WH)
   location as we want to get the stock in replenishment taken into account of
   our product stock total quantity.

Route Configuration
===================

#. You should configure at least a route with a rule that:

    * Pull from the Replenishment stock location.
    * For the stock location you want to (e.g.: WH/Stock)

Location Orderpoint configuration
=================================

#. Go either by the stock location you want to replenish and click on 'Orderpoints'
   or go to Inventory > Configuration > Warehouse > Stock Location Orderpoint
#. Click on 'Create'
#. Set a sequence
#. Choose if the rule will be applied:

    * Automatically (Auto/realtime): at each stock movement on the stock location, the rule will be
      evaluated.
    * Manually (Manual): If set, an action 'Run Replenishment' will be displayed on the rule
      and allow to run it manually.
    * by cron (Scheduled): A cron job will trigger the replenishment rules of this kind.
#. Choose a replenish method:

    * Fill up: The replenishment will be triggered when a move is waiting availability
      and forecast quantity is negative at the location (i.e. min=0). The replenished quantity will
      bring back the forecast quantity to 0 (i.e. max=0) but will be limited to what is available at
      the source location to plan only reservable replenishment moves.
#. Choose the location to replenish
#. Choose the route to use to replenish. The source location will be computed automatically based on
   the route value.
#. Define a procurement group if you want to group some movements together.
#. Define a priority for the created moves.
#. If you want to filter the stock locations that should be taken in consideration
   for product available quantities when triggering a replenishment (e.g.: Supplier locations - 
   to avoid confirmed receptions taken into account), fill in the 
   'Domain to filter locations' field.

Bug Tracker
===========

Bugs are tracked on `GitHub Issues <https://github.com/OCA/stock-logistics-orderpoint/issues>`_.
In case of trouble, please check there if your issue has already been reported.
If you spotted it first, help us to smash it by providing a detailed and welcomed
`feedback <https://github.com/OCA/stock-logistics-orderpoint/issues/new?body=module:%20stock_location_orderpoint%0Aversion:%2016.0%0A%0A**Steps%20to%20reproduce**%0A-%20...%0A%0A**Current%20behavior**%0A%0A**Expected%20behavior**>`_.

Do not contact contributors directly about support or help with technical issues.

Credits
=======

Authors
~~~~~~~

* MT Software
* BCIM

Contributors
~~~~~~~~~~~~

* Michael Tietz (MT Software) <mtietz@mt-software.de>
* Jacques-Etienne Baudoux (BCIM) <je@bcim.be>
* Denis Roussel <denis.roussel@acsone.eu>

Maintainers
~~~~~~~~~~~

This module is maintained by the OCA.

.. image:: https://odoo-community.org/logo.png
   :alt: Odoo Community Association
   :target: https://odoo-community.org

OCA, or the Odoo Community Association, is a nonprofit organization whose
mission is to support the collaborative development of Odoo features and
promote its widespread use.

.. |maintainer-mt-software-de| image:: https://github.com/mt-software-de.png?size=40px
    :target: https://github.com/mt-software-de
    :alt: mt-software-de

Current `maintainer <https://odoo-community.org/page/maintainer-role>`__:

|maintainer-mt-software-de| 

This module is part of the `OCA/stock-logistics-orderpoint <https://github.com/OCA/stock-logistics-orderpoint/tree/16.0/stock_location_orderpoint>`_ project on GitHub.

You are welcome to contribute. To learn how please visit https://odoo-community.org/page/Contribute.
