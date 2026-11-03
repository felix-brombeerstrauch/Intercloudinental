# System components and interfaces

## Component diagram

![Diagram](diagrams/system-component-diagram.drawio.png)

## Interfaces

### Backend - Public Interfaces

#### ExternalAuthApi

Expects:
- request for external authentication in JSON format

Returns one of:
- HTTP redirect response containing a URL to a ExternalAuthView
- HTTP "request denied" response

#### ExternalAuthCbApi

Expects:
- temporary authentication code to request external Access Token and Refresh Token (format not yet specified)

Returns one of:
- response indicating success (format not yet specified)
- response indicating failure (format not yet specified)

#### InternalAuthApi

Expects one of:
- request for access token (format not yet specified)
- request for refresh token (format not yet specified)

Returns one of:
- response with access token (format not yet specified)
- response with refresh token (format not yet specified)
- "request denied" response (format not yet specified)

#### RequestAPI

Expects:
- request in JSON format regarding business logic (but not authorization)

Returns:
- response to request in JSON format

### Backend - Private Interfaces

#### IDriveManager

Expects:
- request in JSON format regarding the addition/removal/update of a drive

Returns:
- response to request in JSON format

#### IExternalTokenStore

Expects:
- request in JSON format regarding the addition/removal/retrieval of an external token

Returns:
- response to request in JSON format

#### IInternalKeyStore

Expects:
- request in JSON format regarding the addition/removal/retrieval of an internal encryption key

Returns:
- response to request in JSON format

#### IInternalRefreshTokenStore

Expects:
- request in JSON format regarding the addition/removal/retrieval of an internal refresh token

Returns:
- response to request in JSON format
