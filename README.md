
# SEC.EDGAR

A .Net library for interacting with the Securities Exchange Commission (SEC) EDGAR System.

## Installation:

Install package via Nuget: https://www.nuget.org/packages/SEC.EDGAR/<br><br>
PM> Install-Package SEC.EDGAR<br><br>

## Instructions:

Create an EDGAR object.<br><br>
var edgar = new EDGAR("productKey", "e-mailAddress", RequestCacheLevel.BypassCache);

The library does not cache calls. You can change cache option.<br><br>
var edgar = new EDGAR("productKey", "e-mailAddress", RequestCacheLevel.BypassCache); //Default Option

## Sample API Calls

<b><u>GetCompanyInfo</u></b><br>
var company = edgar.GetCompanyInfo(string companyId); //Company Id can only be company's stock symbol or SEC CIK#

<b><u>GetCompanyFilings</u></b><br>
IEnumerable\<Filings\> GetCompanyFilings(string companyId, filingType, string ownership, string filingBeforeDate); //Company Id can only be company's stock symbol or SEC CIK#.

<b><u>GetOwnerFilings</u></b><br>
IEnumerable\<Filings\> GetOwnerFilings(string ownerId, string filingType, string ownership, string filingBeforeDate); //Owner Id can only be insider owner's SEC CIK#.

<b><u>GetOwnerDetails</u></b><br>
IEnumerable\<Owner\> GetOwnerDetails(string companyId); //Company Id can only be company's stock symbol or SEC CIK#.

<b><u>DownloadFile</u></b><br>
int x = edgar.DownloadFile(string url, string directoryPath, boolean useDefaultFileName, string FileName);




