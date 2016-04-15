![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
![](http://www.adviso.ca/wp-content/themes/adviso/images/structure/logo.png)


# SYSTEM INTEGRATION SPECIFICATIONS FOR AIR CANADA: MANAGE FLIGHT BOOKING PROCESS




# 1. Project Overview
***


The goal of this project is to update the analytics implementation on Air Canada's digital assets. The current document provides a complete overview of the tagging requirements for provide a complete overview of all tagging requirements for Air CanadaÃ¢â‚¬â„¢s Manage Booking Flow.


Document Revision History
=========================

Revision Number | Date| Revision Description | Author
------------ | ------------- | ------------ | ---------
0.1 |12/06/2014 | Initial Draft Version for Review | Alexandre Cayla, Digito
0.2 | 15/10/2014 | Updated Draft to include page code (new website)| Alexandre Cayla, Digito
0.3 |29/10/2014 |Updated Draft with DigitalData Implementation Instruction for All pages, Home Page, Flight Booking | Ai Thanh Ho, Adviso
0.4|13/11/2014| Updated Draft with DigitalData Implementation for Manage My Booking |Ai Thanh Ho, Adviso
0.5 | 20/11/2014| Integration with Bitbucket |Ai Thanh Ho, Adviso
0.6 | 31/03/2015| SIS First draft |Ai Thanh Ho, Adviso
0.7 | 24/04/2015| Refactoring digitalData  |Ai Thanh Ho, Adviso
1.0 | 05/05/2015| SIS final |Ai Thanh Ho, Adviso
2.0 | 26/06/2015| SIS for new mockup (May)|Ai Thanh Ho, Adviso
2.1 | 24/07/2015| SIS for new mockup (June) |Ai Thanh Ho, Adviso
2.2 | 09/09/2015| Minor clarifications added to tagging instructions | Alexandre Cayla, Adviso






# 2. Document Overview
***

To ensure that all tags have access to the same data and can be managed easily and properly, Adobe Tag Manager will be used in conjunction to a dataLayer (digitalData). All user interactions with the website will be divided into use case. Each use case contains information about:

- Short explanation of what is being tracked
- Implementation Instructions with key elements of the digitalData datalayer
- Sample code
- Validation instructions


The outline of this document is the following:

- [1. Project Overview](#1-project-overview)
- [2. Document Overview](#2-document-overview)
- [3. digitalData data layer object](#3-digitaldata-data-layer-object)
- [4. General validation instructions](#4-general-validation-instructions)
- [5. Integration instructions](#5-integration-instructions)
    - [5.1 General instructions](#51-general-instructions)
    - [5.2 Campaign tagging](#52-campaign-tagging)
        - [1 Internal promotion](#1-internal-promotion)
        - [2 Internal offers](#2-internal-offers)
    - [5.3 Manage My Booking process](#53-manage-my-booking-process)
        - [Diagram](#diagram)
        - [Process details](#process-details)
        - [1 View Manage My Bookings - Booking List](#1-view-manage-my-bookings---booking-list)
        - [2 View Manage My Bookings - Booking Details](#2-view-manage-my-bookings---booking-details)
        - [3 View Manage My Bookings - Change trip page](#3-view-manage-my-bookings---change-trip-page)
        - [4a View Manage My Bookings - Change flights](#4a-view-manage-my-bookings---change-flights)
        - [4b View Manage My Bookings - Add flights](#4b-view-manage-my-bookings---add-flights)
        - [5 View Flight Search Results page](#5-view-flight-search-results-page)
            - [5.1 View a flight](#51-view-a-flight)
            - [5.2 Select flight](#52-select-flight)
        - [6 View Flight Upgrade page](#6-view-flight-upgrade-page)
            - [6.1 Change flight](#61-change-flight)
            - [6.2 Select a flight upgrade](#62-select-a-flight-upgrade)
            - [6.3 Reselect a flight upgrade](#63-reselect-a-flight-upgrade)
        - [7 Share itinerary page](#7-share-itinerary-page)
            - [7.1 Send Email Itinerary](#71-send-email-itinerary)
        - [8 View Select Travel option page](#8-view-select-travel-option-page)
            - [8.1 View an ancillary](#81-view-an-ancillary)
            - [8.2 Select ancillary](#82-select-ancillary)
            - [8.3 Remove ancillary](#83-remove-ancillary)
        - [9 View Passengers page](#9-view-passengers-page)
        - [10 View Seat Selection page](#10-view-seat-selection-page)
        - [11 View seat map page](#11-view-seat-map-page)
            - [11.1 View Seat](#111-view-seat)
            - [11.2 Select Seat](#112-select-seat)
            - [11.3 Reselect Seat](#113-reselect-seat)
        - [12 View Payment page](#12-view-payment-page)
            - [12.1 View insurance](#121-view-insurance)
            - [12.2 Select insurance](#122-select-insurance)
            - [12.3 Reselect insurance](#123-reselect-insurance)
        - [13 View Authentication page](#13-view-authentication-page)
        - [14 View Confirmation page](#14-view-confirmation-page)
        - [15 View Manage My Bookings - Cancellation page](#15-view-manage-my-bookings---cancellation-page)
    - [5.4 Other use cases](OtherUseCases.md)
        - [View error pages](OtherUseCases.md#view-error-pages)
        - [Form errors](OtherUseCases.md#form-errors)
        - [All other pages](OtherUseCases.md#all-other-pages)
- [Appendices](#appendices)
    - [digitalData data layer object](#digitaldata-data-layer-object)
    - [Troubleshooting](#troubleshooting)
        - [Common errors](#common-errors)
        


# 3. digitalData data layer object
***

The dataLayers primary goal is to expose relevant data elements (such as the name of a page, it's section, the total of a transaction, etc.) to the tag management system. The data elements are organised in different JavaScript objects that contain all related data elements. For example:

- `page`

- `users`

- `events`

- `cart`

- `products`

- `transactions`


Collectively, these objects constitute the `digitalData` object. The contents of these objects is either set in the page code or updated using the `digitalData.events.push` method.

For more information on how to track event or to extend digitalData, see Appendix 1.


# 4. General validation instructions
***

In order to validate that the code has been integrated correctly, follow these steps:

1) Open the console of the web browser by pressing F12 (for Internet Explorer) or Control-Shift-J for Chrome

![Validation Console](http://aiscreenshot.s3.amazonaws.com/Validation_Console.png)

2) Refresh the page or follow the use case (for example: click on a button/ component) to trigger
the event

3) Type `digitalData` and press enter.

For common errors and how to fix them, please refer to Appendix 2.



# 5. Integration instructions
***

***

## 5.1 General instructions

[See more details here](GeneralInstructions.md)

## 5.2 Campaign tagging

[See more details here](CampaignTagging.md)


## 5.3 Manage My Booking process

[See more details here](ManageBookingProcess.md)



## 5.4 Other use cases

[See more details here](OtherUseCases.md)


# Appendices

## digitalData data layer object

For more information, visit our Bitbucket repository at [https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary](https://bitbucket.org/adviso/customer-air-canada-digital-data-layer-dictionary)

## Troubleshooting

### Common errors

1) Syntax Error
-	If the console shows some error warnings such as ``Uncaught Syntax Error: Unexpected
identifier``, go to the javascript code to fix the syntax.

![Syntax Error](http://aiscreenshot.s3.amazonaws.com/Validation_SyntaxError.png)

-	If there is no error, continue to step 3.

2) _satellite is not defined

- Type: ``_satellite`` in the console

- If the console displays ``ReferenceError: _satellite is not defined``, check if this code snippet is correctly included in the ``<head>`` section.

````html
<script src="//assets.adobedtm.com/a0e4257e187c718dbef1dd231d87385336b39a7a/satelliteLib-9ccb4de22acfc5080eefa87b51427f642289f701.js">
</script>
````

4) digitalData is not defined

- Type: ``console.log(digitalData)`` in the console

- If the console displays ``ReferenceError: digitalData is not defined``, check if this code snippet is included in the ``<head>``

````html
<script type="text/javascript">
   var digitalData=window.digitalData||{};
   digitalData.events=window.digitalData.events||[];
</script>
````

![digitalData Not Defined](http://aiscreenshot.s3.amazonaws.com/Validation_NotDefined.png)

5) For all the use cases check if all necessary data are correctly populated

![digitalData](http://aiscreenshot.s3.amazonaws.com/Validation_DigitalData.png)
