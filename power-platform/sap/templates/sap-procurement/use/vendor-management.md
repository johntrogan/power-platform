---
title: Use the SAP Vendor Management app
description: Learn how you can view, update, and create a vendor in SAP using Microsoft's SAP Vendor Management app for Microsoft Power Platform.
author: jongilman88
ms.author: jongilman
contributors:
  - EllenWehrle
  - microsoft-george
  - robinsonshields
  - tverhasselt
  - ryanb58
  - Wrighttyler
  - shanep
ms.reviewer: ellenwehrle
ms.topic: get-started
ms.date: 1/8/2024
ms.custom: bap-template
ms.service: power-platform
ms.subservice: solution-templates
---

# Get started using the SAP Vendor Management app

The SAP Vendor Management app is part of the SAP Procurement solution for Microsoft Power Platform. It allows you to do several functions in SAP quicker and easier than using SAP GUI. You can view, update, and create a vendor.

## View vendor information

You can load existing vendor information three different ways:

- Select a recent vendor from a dropdown list.
- Search for a vendor.
- Enter a known vendor ID.

:::image type="content" source="media/vendor-management/sap-procure-vendors-ed.png" alt-text="Image of Microsoft's SAP Procurement vendor app for Power Platform.":::

### Select a vendor invoice

You can select a recently viewed vendor from the _Recently Searched Vendors_ list. Choose a vendor from the list to load that vendor's record onto your screen.

### Search for a vendor

You can search for a vendor using known search criteria.

  1. Select the **Search Vendor** button to open the vendor search screen.
  1. Enter your search criteria into one or more of the following fields:
      - Vendor name
      - Street
      - City
      - Country
      - State/Province
      - Postal Code
   :::image type="content" source="media/vendor-management/vendor-search.png" alt-text="Search for a vendor screen.":::
  1. Select **Search** to see your results.
  1. Select the _vendor_ you want to view from the list of results.

### Enter a vendor ID

You can enter a known vendor ID into the _Enter Vendor ID_ field and select **Search** to retrieve the vendor record from SAP and display the information on your screen.

## Update vendor information

Once an existing vendor record is loaded to the app, making changes is straightforward. Select the **Edit Vendor** button to make updates.

## Create a vendor

Creating a vendor is straightforward. Select **New Vendor** to start a new vendor record.

### Enter the vendor details

Provide the vendor name, account group, and address on the first page and select **Next**.

### Add purchasing organizations

For each vendor purchasing organization, enter in the required information and select **Add Purchasing Organization**. Select **Next** when all purchasing organizations have been added.

### Add company codes

For each vendor company code, enter in the required information and select **Add Company Code**. Select **Next** when all company codes have been added.

### Add phone numbers

For each vendor phone number, enter in the required information and select **Add Phone Number**. Select **Next** when all phone numbers have been added.

### Add email addresses

For each vendor email address, enter in the required information and select **Add Email Address**. Select **Review & Submit** when all email addresses have been added.

### Submit

Review the information you entered and select **Submit** to create the new vendor.

## Field mappings

The tables provide vendor screen to function module field mappings.

### RFC_READ_TABLE mapping

| Area                    | Table | Field | Description             |
|-------------------------|-------|-------|-------------------------|
| Header                  | LFA1  | LIFNR | Vendor                  |
| Header                  | LFA1  | LAND1 | Country                 |
| Header                  | LFA1  | NAME1 | Vendor name             |
| Header                  | LFA1  | ORTO1 | City                    |
| Header                  | LFA1  | PSTLZ | Postal code             |
| Header                  | LFA1  | STRAS | Street                  |
| Header                  | LFA1  | REGIO | State                   |
| Header                  | LFA1  | KTOKK | Account group           |
| Company                 | LFB1  | AKONT | General ledger account  |
| Company                 | LFB1  | BUKRS | Company code            |
| Company                 | LFB1  | ZTERM | Payment terms           |
| Company                 | LFB1  | ZWELS | Payment method          |
| Purchasing Organization | LFM1  | EKGRP | Purchasing group        |
| Purchasing Organization | LFM1  | EKORG | Purchasing organization |
| Purchasing Organization | LFM1  | WAERS | Currency                |
| Purchasing Organization | LFM1  | ZTERM | Payment terms           |

### BAPI_ADDRESSORG_GETDETAIL mapping

| Structure  | Field      | Label     |
|------------|------------|-----------|
| BAPIADSMTP | E_MAIL     | Email     |
| BAPIADSMTP | STD_NO     | Default   |
| BAPIADSMTP | CONSNUMBER | ID        |
| BAPIADTEL  | COUNTRY    | Country   |
| BAPIADTEL  | TELEPHONE  | Phone     |
| BAPIADTEL  | EXTENSION  | Extension |
| BAPIADTEL  | STD_NO     | Default   |
| BAPIADTEL  | CONSNUMBER | ID        |

### IDOC_INBOUND_SYNCHRONOUS mapping

| Segment | Field | Label                  | Comment               |
|---------|-------|------------------------|-----------------------|
| E1LFA1M | LIFNR | Vendor                 | Blank during _Create_ |
| E1LFA1M | KTOKK | AccountGroup           |                       |
| E1LFA1M | LAND1 | Country                |                       |
| E1LFA1M | NAME1 | VendorName             |                       |
| E1LFA1M | ORTO1 | City                   |                       |
| E1LFA1M | PSTLZ | PostalCode             |                       |
| E1LFA1M | REGIO | State                  |                       |
| E1LFA1M | STRAS | Street                 |                       |
| E1LFB1M | MSGFN | CrudType               |                       |
| E1LFB1M | BUKRS | CompanyCode            |                       |
| E1LFB1M | LOEVM | CrudType               | _X_ for Delete        |
| E1LFB1M | AKONT | GLAccount              |                       |
| E1LFB1M | ZWELS | PaymentMethods         |                       |
| E1LFB1M | ZTERM | PaymentTerms           |                       |
| E1LFM1M | MSGFN | CrudType               |                       |
| E1LFM1M | EKORG | PurchasingOrganization |                       |
| E1LFM1M | LOEVM | CrudType               | _X_ for Delete        |
| E1LFM1M | WAERS | Currency               |                       |
| E1LFM1M | ZTERM | PaymentTerms           |                       |
| E1LFM1M | EKGRP | PurchasingGroup        |                       |

### BAPI_ADDRESSORG_CHANGE mapping

| Structure  | Field      | Label     |
|------------|------------|-----------|
| BAPIADSMTP | E_MAIL     | Email     |
| BAPIADSMTP | STD_NO     | Default   |
| BAPIADSMTP | CONSNUMBER | ID        |
| BAPIADTEL  | COUNTRY    | Country   |
| BAPIADTEL  | TELEPHONE  | Phone     |
| BAPIADTEL  | EXTENSION  | Extension |
| BAPIADTEL  | STD_NO     | Default   |
| BAPIADTEL  | CONSNUMBER | ID        |

### See also

- [SAP Vendor Management app](vendor-management.md)
- [SAP Requisition Management app](requisition-management.md)
- [SAP Purchase Order Management app](purchase-order-management.md)
- [SAP Goods Receipt Management app](goods-receipt-management.md)
- [SAP Vendor Invoice Management app](vendor-invoice-management.md)
- [SAP Vendor Payment management app](payment-management.md)
