
# SEC.EDGAR

A .Net library for interacting with the Securities Exchange Commission (SEC) EDGAR System.

More than 30 filing types can be retrieved..., including:

3 Reports - Initial statement of beneficial ownership of securities.
4 Reports - Statement of changes in beneficial ownership of securities.
4 Amended Report - Amended Statement of changes in beneficial ownership of securities
5 Reports - Annual statement of changes in beneficial ownership of securities.
8K Reports - Current report, items 7.01 and 9.01.
10K Reports.
10K Amended Reports.
10-Q Report - Quarterly report [Sections 13 or 15(d)].
11K Report - Annual report of employee stock purchase, savings and similar plans.
13-F Reports.
13F-HR Reports - Quarterly report filed by institutional managers, Holdings.
Annual Reports.
Semi-Annual Reports.
Prospectuses.
Summary Prospectuses.
...and more.


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




