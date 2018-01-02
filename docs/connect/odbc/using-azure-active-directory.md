---
title: "Using Azure Active Directory with the ODBC Driver | Microsoft Docs"
ms.custom: ""
ms.date: "04/18/2017"
ms.prod: "sql-non-specified"
ms.prod_service: "drivers"
ms.service: ""
ms.component: "odbc"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "drivers"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 52205f03-ff29-4254-bfa8-07cced155c86
caps.latest.revision: 9
author: "MightyPen"
ms.author: "genemi"
manager: "jhubbard"
ms.workload: "Inactive"
---
# Using Azure Active Directory with the ODBC Driver
[!INCLUDE[Driver_ODBC_Download](../../includes/driver_odbc_download.md)]

## Purpose

The ODBC Driver 13.1 for SQL Server allows ODBC applications to connect to an instance of SQL Azure using a federated identity in Azure Active Directory with a username/password, an Azure Active Directory access token (Windows driver only), or Windows Integrated Authentication (Windows driver only). This is accomplished through the use of new DSN and connection string keywords, and connection attributes.

## New and/or Modified DSN and Connection String Keywords

The `Authentication` keyword can be used when connecting with a DSN or connection string to control the authentication mode. The value set in the connection string overrides that in the DSN, if provided. The _pre-attribute value_ of the `Authentication` setting is the value computed from the connection string and DSN values.

|Name|Values|Default|Description|
|-|-|-|-|
|`Authentication`|(not set), (empty string), `SqlPassword`, `ActiveDirectoryPassword`, `ActiveDirectoryIntegrated`|(not set)|Controls the authentication mode.<table><tr><th>Value<th>Description<tr><td>(not set)<td>Authentication mode determined by other keywords (existing legacy connection options.)<tr><td>(empty string)<td>(Connection string only.) Override and unset an `Authentication` value set in the DSN.<tr><td>`SqlPassword`<td>Directly authenticate to a SQL Server instance using a username and password.<tr><td>`ActiveDirectoryPassword`<td>Authenticate with an Azure Active Directory identity using a username and password.<tr><td>`ActiveDirectoryIntegrated`<td>_Windows driver only_. Authenticate with an Azure Active Directory identity using integrated authentication.</table>|
|`Encrypt`|(not set), `Yes`, `No`|(see description)|Controls encryption for a connection. If the pre-attribute value of the `Authentication` setting is not _none_, the default is `Yes`. Otherwise, the default is `No`. The pre-attribute value of Encryption is `Yes` if the value is set to `Yes` in either the DSN or connection string.|

## New and/or Modified Connection Attributes

The following pre-connect connection attributes have either been introduced or modified to support Azure Active Directory authentication. When a connection attribute has a corresponding connection string or DSN keyword and is set, the connection attribute takes precedence.

|Attribute|Type|Values|Default|Description|
|-|-|-|-|-|
|`SQL_COPT_SS_AUTHENTICATION`|`SQL_IS_INTEGER`|`SQL_AU_NONE`, `SQL_AU_PASSWORD`, `SQL_AU_AD_INTEGRATED`, `SQL_AU_AD_PASSWORD`, `SQL_AU_RESET`|(not set)|See description of `Authentication` keyword above. `SQL_AU_NONE` is provided in order to explicitly override a set `Authentication` value in the DSN and/or connection string, while `SQL_AU_RESET` unsets the attribute if it was set, allowing the DSN or connection string value to take precedence.|
|`SQL_COPT_SS_ACCESS_TOKEN`|`SQL_IS_POINTER`|Pointer to `ACCESSTOKEN` or NULL|NULL|_Windows driver only_. If non-null, specifies the AzureAD Access Token to use. It is an error to specify an access token and also `UID`, `PWD`, `Trusted_Connection`, or `Authentication` connection string keywords or their equivalent attributes.|
|`SQL_COPT_SS_ENCRYPT`|`SQL_IS_INTEGER`|`SQL_EN_OFF`, `SQL_EN_ON`|(see description)|Controls encryption for a connection. `SQL_EN_OFF` and `SQL_EN_ON` disable and enable encryption, respectively. If the pre-attribute value of the `Authentication` setting is not _none_ or `SQL_COPT_SS_ACCESS_TOKEN` is set, and `Encrypt` was not specified in either the DSN or connection string, the default is `SQL_EN_ON`. Otherwise, the default is `SQL_EN_OFF`. The effective value of this attribute controls [whether encryption will be used for the connection.](https://docs.microsoft.com/en-us/sql/relational-databases/native-client/features/using-encryption-without-validation)|
|`SQL_COPT_SS_OLDPWD`|\-|\-|\-|Not supported with Azure Active Directory, since password changes to AAD principals cannot be accomplished through an ODBC connection. <br><br>Password expiration for SQL Server Authentication was introduced in SQL Server 2005. The `SQL_COPT_SS_OLDPWD` attribute was added to allow the client to provide both the old and the new password for the connection. When this property is set, the provider will not use the connection pool for the first connection or for subsequent connections, since the connection string will contain the "old password" which has now changed.|
|`SQL_COPT_SS_INTEGRATED_SECURITY`|`SQL_IS_INTEGER`|`SQL_IS_OFF`,`SQL_IS_ON`|`SQL_IS_OFF`|_Deprecated_; use `SQL_COPT_SS_AUTHENTICATION` set to `SQL_AU_AD_INTEGRATED` instead. <br><br>Forces use of Windows Authentication (Kerberos on Linux and macOS) for access validation on server login. When Windows Authentication is used, the driver ignores user identifier and password values provided as part of `SQLConnect`, `SQLDriverConnect`, or `SQLBrowseConnect` processing.|

## UI Additions for Azure Active Directory (Windows driver only)

The DSN setup and connection UIs of the driver have been enhanced with the additional options necessary for using authentication with Azure AD.

### Creating and editing DSNs in the UI

It is possible to use the new Azure AD authentication options when creating or editing an existing DSN using the driver's setup UI:

`Authentication=ActiveDirectoryIntegrated` for Azure Active Directory Integrated authentication to SQL Azure

![CreateNewDSN3.png](windows/CreateNewDSN3.png)

`Authentication=ActiveDirectoryPassword` for Azure Active Directory username/password authentication to SQL Azure

![CreateNewDSN4.png](windows/CreateNewDSN4.png)

`Authentication=SqlPassword` for username/password authentication to SQL Server (Azure or otherwise)

![CreateNewDSN.png](windows/CreateNewDSN.png)

`Trusted_Connection=Yes` for Windows legacy SSPI integrated authentication

![CreateNewDSN2.png](windows/CreateNewDSN2.png)

The four options correspond to `Trusted_Connection=Yes` (existing legacy Windows SSPI-only integrated authentication) and `Authentication=` `ActiveDirectoryIntegrated`, `SqlPassword`, and `ActiveDirectoryPassword`, respectively.

### SQLDriverConnect Prompt (Windows driver only)

The prompt dialog displayed by SQLDriverConnect when it requests information required to complete the connection contains two new options for Azure AD authentication:

![SQLServerLogin.png](windows/SQLServerLogin.png)

These options correspond to the same four available in the DSN setup UI above.

### Example connection strings
1. SQL Server Authentication – legacy syntax. Server certificate is not validated, and encryption is used only if the server enforces it. The username/password is passed in the connection string.
`server=Server;database=Database;UID=UserName;PWD=Password;`
2. SQL Authentication – new syntax. The client requests encryption (the default value of `Encrypt` is `true`) and the server certificate gets validated, regardless of the encryption setting (unless `TrustServerCertificate` is set to `true`). The username/password is passed in the connection string.
 `server=Server;database=Database;UID=UserName;PWD=Password;Authentication=SqlPassword;`
3. Integrated Windows Authentication (Kerberos on Linux and macOS) using SSPI (to SQL Server or SQL IaaS) – current syntax. Server certificate is not validated, unless encryption is used. 
`server=Server;database=Database;Trusted_Connection=yes;`
4. (_Windows driver only_.) Integrated Windows Authentication using SSPI (if the target database is in SQL Server or SQL IaaS) – new syntax. The client requests encryption (the default value of `Encrypt` is `true`) and the server certificate gets validated, regardless of the encryption setting (unless `TrustServerCertificate` is set to `true`). 
`server=Server;database=Database;Authentication=ActiveDirectoryIntegrated;`
5. AAD Username/Password Authentication (if the target database is in Azure SQL DB). Server certificate gets validated, regardless of the encryption setting (unless `TrustServerCertificate` is set to `true`). The username/password is passed in the connection string. 
`server=Server;database=Database;UID=UserName;PWD=Password;Authentication=ActiveDirectoryPassword;`
6. (_Windows driver only_.) Integrated Windows Authentication using ADAL, which involves redeeming Windows account credentials for an AAD-issued access token, assuming the target database is in Azure SQL Database. Server certificate gets validated, regardless of the encryption setting (unless `TrustServerCertificate` is set to `true`). 
`server=Server;database=Database; Authentication=ActiveDirectoryIntegrated;`

> [!NOTE] 
>- When using the new Active Directory options with the Windows ODBC driver, ensure that the [Active Directory Authentication Library for SQL Server](http://go.microsoft.com/fwlink/?LinkID=513072) has been installed. The Linux and macOS drivers do not require any additional dependencies for authenticating with Azure Active Directory.
>- To connect using a SQL Server account username and password, you may now use the new `SqlPassword` option, which is recommended especially for SQL Azure since this option enables more secure connection defaults.
>- To connect using an Azure Active Directory account username and password, specify `Authentication=ActiveDirectoryPassword` in the connection string and the `UID` and `PWD` keywords with the username and password, respectively.
>- To connect using Windows Integrated or Active Directory Integrated (Windows driver only) authentication, specify `Authentication=ActiveDirectoryIntegrated` in the connection string. The driver will choose the correct authentication mode automatically. `UID` and `PWD` must not be specified.

## Authenticating with an Access Token (Windows driver only)

The `SQL_COPT_SS_ACCESS_TOKEN` pre-connection attribute allows the use of an access token obtained from Azure AD for authentication instead of username and password, and also bypasses the negotiation and obtaining of an access token by the driver. To use an access token, set the `SQL_COPT_SS_ACCESS_TOKEN` connection attribute to a pointer to an `ACCESSTOKEN` structure:

~~~
typedef struct AccessToken
{
    DWORD dataSize;
    BYTE data[];
} ACCESSTOKEN;
~~~

The `ACCESSTOKEN` is a variable-length structure consisting of a 4-byte _length_ followed by _length_ bytes of opaque data that form the access token. Due to how SQL Server handles access tokens, one obtained via an [OAuth 2.0](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-authentication-scenarios) JSON response must be expanded so that each byte is followed by a 0 padding byte, similar to a UCS-2 string containing only ASCII characters; however, the token is an opaque value and the length specified, in bytes, must NOT include any null terminator. Because of their considerable length and format constraints, this method of authentication is only available programmatically via the `SQL_COPT_SS_ACCESS_TOKEN` coonnection attribute; there is no corresponding DSN or connection string keyword. The connection string must not contain `UID`, `PWD`, `Authentication`, or `Trusted_Connection` keywords.

## Azure Active Directory Authentication Sample Code

The following sample shows the code required to connect to SQL Server using Azure Active Directory with connection keywords. Note that there is no need to change the application code itself; the connection string, or DSN if one is used, is the only modification needed to use AAD for authentication:
~~~
    ...
    SQLCHAR connString[] = "Driver={ODBC Driver 13 for SQL Server};Server={server};UID=myuser;PWD=myPass;Authentication=ActiveDirectoryPassword"
    ...
    SQLDriverConnect(hDbc, NULL, connString, SQL_NTS, NULL, 0, NULL, SQL_DRIVER_NOPROMPT);	
    ...
~~~
The following sample shows the code required to connect to SQL Server using Azure Active Directory with access token authentication. In this case, it is necessary to modify application code to process the access token and set the associated connection attribute.
~~~
    SQLCHAR connString[] = "Driver={ODBC Driver 13 for SQL Server};Server={server}"
    SQLCHAR accessToken[] = "eyJ0eXAiOi..."; // In the format extracted from an OAuth JSON response
    ...
    DWORD dataSize = 2 * strlen(accessToken);
    ACCESSTOKEN *pAccToken = malloc(sizeof(ACCESSTOKEN) + dataSize);
    pAccToken->dataSize = dataSize;
    // Expand access token with padding bytes
    for(int i = 0, j = 0; i < dataSize; i += 2, j++) {
        pAccToken->data[i] = accessToken[j];
        pAccToken->data[i+1] = 0;
    }
    ...
    SQLSetConnectAttr(hDbc, SQL_COPT_SS_ACCESS_TOKEN, (SQLPOINTER)pAccToken, SQL_IS_POINTER);
    SQLDriverConnect(hDbc, NULL, connString, SQL_NTS, NULL, 0, NULL, SQL_DRIVER_NOPROMPT);		
    ...
    free(pAccToken);
~~~

## See Also
[Token-based authentication support for Azure SQL DB using Azure AD auth](https://blogs.msdn.microsoft.com/sqlsecurity/2016/02/09/token-based-authentication-support-for-azure-sql-db-using-azure-ad-auth)

