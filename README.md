Django Azure AD Auth
======================

*Django Azure AD Auth* allows you to authenticate through Azure Active Directory.

Installation
------------

Run `pip install django-azure-ad-auth`

Add the `AzureActiveDirectoryBackend` to your `AUTHENTICATION_BACKENDS` setting:

```python
AUTHENTICATION_BACKENDS = (
    ...
    'azure_ad_auth.backends.AzureActiveDirectoryBackend',
)
```

Settings
--------

### AAD_TENANT_ID

The Azure Tenant ID. It can be found in the URL of the Azure Management Portal.

### AAD_CLIENT_ID

The Azure Application Client ID.


### AAD_AUTHORITY

**default:** `'https://login.microsoftonline.com'`
The domain that is used for authorization, the federation metadata document, and loggin out.

### AAD_SCOPE

**default:** `'openid'`
OAuth scope parameter.

### AAD_RESPONSE_TYPE

**default:** `'id_token'`
Tells OAuth to return a JWT token in its response.

### AAD_RESPONSE_MODE

**default:** `'form_post'`
Defines how the response parameters are returned. Valid choices are `fragment` or `form_post`.

### AAD_USER_CREATION

**default:** `True`
Allow creation of new users after successful authentication.

### AAD_EMAIL_FIELD

**default:** `upn`
Select the unique field to be used for user creation.

### AAD_USER_MAPPING

**default:** `{}`
Map fields from the token to the user, to be used on creation.

### AAD_USER_STATIC_MAPPING

**default:** `{}`
Map static values to user fields on creation.

### AAD_GROUP_MAPPING

**default:** `{}`
Map group ids to group names for user permissions.

### AAD_GROUP_STATIC_MAPPING

**default:** `set()`
Map static groups to user. 
