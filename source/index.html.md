---
title: DelPlaya - Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - html: HTML

toc_footers:
  - <a href='https://www.delplaya.com'>DelPlaya</a>
  - <a href='https://miramar.delplaya.com/'>DelPlaya Miramar</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:

search: true
---

# Introduction

Our engagement system reports event-level data that is coded to look for campaign related activity. 

A client-side GET request with key-value pairs attributes engagement to campaigns and passes additional pertinent session information.

# Impressions

## Parameters

Key | Description | Example Value
--------- | ------- | -----------
`d`	| This is the date of the record in Y-M-D H:M:S format | 2019-01-01 00:00:00
`deviceOS` | The device OS expressed as iOS or Android | iOS or Android
`deviceIFA`	| Android Advertising ID or Apple IDFA | 6bd62ee2-3710-46a8-a3a0-c43f9837265b
`lattitude`	| Latitude with up to 7 digits precision | 33.438747
`longitutde` | Longitude with up to 7 digits precision | -82.04986
`userAgent` | URL Encoded USER AGENT of device | Mozilla%2F5.0%20%28iPhone%3B%20<br/>CPU%20iPhone%20OS%2012_1_2%20<br/>like%20Mac%20OS%20X%29%20<br/>AppleWebKit%2F605.1.15%20%28<br/>KHTML%2C%20like%20Gecko<br/>%29%20Mobile%2F16C101
`adWidth` | Numeric Ad Width in Pixels| 300
`adHeight` | Numeric Ad Height in Pixels | 200
`campaignID` | Alpha Numeric Campaign ID |12345
`bannerID` | Alpha Numeric Banner ID | 12345
`pubID` | The assigned ID of a specific publisher grouping (apps or sites) | XYZ1234
`invType` | Display or Video| display
`deviceType` | The numeric ID for the type of device. (i.e iPhone=4, iPad=5) | 4
`country`	| The ISO code for the country | USA
`bid`	| Assigned Business Identifier |  XYZABC1234
`gender` | M = male, F = Femal, O = Other or unknown | F
`age` | The numeric age of the user. In some cases it might be a specific age (22,52, 65) other wise it will be a decade (20,30,40) | 40
`ip` | The IP4 ip address of the record | 127.0.0.1
`engagementType` | Numeric engagementType ID | Integer
`orderValue` | Numeric order Value | 10.00
`orderID`	| Alphanumeric orderID (Unique) | ABC123

# Engagements

## Landing Page Load

> Example Usage

```html
<img  src="https://insight.delplaya.com/p/engagement.php?bid=XYZABC1234
                                                        &engagementType=1" 
      width="1" 
      height="1" 
      border="0" 
      alt="cookie">
```



A pixel is placed on the landing page associated with the banner click-through link. This measurement reports the load of the landing page and shows activity like how much click bounce there is for a campaign. 


### URL Parameters

Key | Description | Example Value
--------- | ------- | -----------
<span class="red">*</span> `bid` | Alphanumeric Hash | XYZABC1234
<span class="red">*</span> `engagementType` | Numeric engagementType ID | 3



## GEO confirmed store visit


This type of request uses device location detection. This signal is fired on the server-side once a device is identified to have been seen in a predefined geo area (typically a building or event area)

### Parameters

Key | Description | Example Value
--------- | ------- | -----------
`bundleID` | BundleID for Android or Numeric AppStore ID for iOS | com.MyApp or 123456789
`deviceOS` | iOS or Android | iOS or Android
`deviceIFA` | Android Advertising ID or Apple IDFA | 6bd62ee2-3710-46a8-a3a0-c43f9837265b
`lattitude` | Latitude with up to 7 digits precision| 33.438747
`longitude` | Longitude with up to 7 digits precision | -82.04986
`userAgent` | URL Encoded USER AGENT of device | Mozilla%2F5.0%20%28iPhone%3B%20<br/>CPU%20iPhone%20OS%2012_1_2%20<br/>like%20Mac%20OS%20X%29%20<br/>AppleWebKit%2F605.1.15%20%28<br/>KHTML%2C%20like%20Gecko<br/>%29%20Mobile%2F16C101
`adWidth` | Numeric Ad Width in Pixels| 300
`adHeight` | Numeric Ad Height in Pixels | 200
`campaignID` | Alpha Numeric Campaign ID |12345
`bannerID` | Alpha Numeric Banner ID | 12345
`pubID` |  The assigned ID of a specific publisher grouping (apps or sites) | XYZ1234
`invType` | Display or Video| display
`costCPM` | Cost of Acquisition| 10.00
`deviceType` | Numerical Device Type (4 = phone & 5 = Tablet) | 4
`auctionID` | Unique ID for originating Auction | ABCE1234
`country` | The ISO code for the country | USA
`appname` | URL Encoded Alpha Numeric App name | My%20App
`gender` | F for female, M for Male, O for Other | M
`age` | Numeric Age | 58
`winDomain` | Subdomain + base domain of advertiser | www.advertiser.com
`engagement` | Numerical EngagementTypeID | 2
<span class="red">*</span> `bid` | Assigned API ID | Assigned - Ask account Rep



## Confirmation Page Load

> Usage Example:

```html
<img src="https://insight.delplaya.com/p/engagement.php?bid=XYZABC1234
                                                       &engagementType=3
                                                       &orderID=ABC123
                                                       &orderValue=100.00" 
    width="1" 
    height="1" 
    border="0" 
    alt="cookie">
```

This engagement type is reported by placing a pixel on the confirmation page. This will track actual mobile web conversions that originated by either a view or a click from a served advertisement. Optional parameters include sale information (i.e. order amount, order quantity etc.)

### URL Parameters

Key | Description | Example Value
--------- | ------- | -----------
<span class="red">*</span> `bid` | Alphanumeric Hash | XYZABC1234
<span class="red">*</span>`engagementType` | Numeric engagementType ID | 3
`orderID` | Alphanumeric orderID | ABC123
`orderValue` | Numeric order Value | 100.00

## Affinity Click

> Usage Example:

```html
Link:
http://insight.delplaya.com/p/engagement.php?&bid=XYZABC1234
                                             &engagementType=4
                                             &url=http%3A%2F%2Fdelplaya.com
```

This engagement type reports an ad engagement that checks for an active cookie and forwards to another website or application and counted as a conversion. All campaign and action history data is stored in the redirection process. 

### URL Parameters

Key | Description | Example Value
-------- | ------- | -----------
<span class="red">*</span> `bid` | Alphanumeric Hash | XYZABC1234
<span class="red">*</span> `engagementType` | Numeric engagementType ID | 4
`url` | URL encoded destination | http%3A%2F%2Fdelplaya.com



