# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

## [Unreleased]
### Added

### Changed


## 0.1.8 - 2016-10-10
### Added
- Add new Status code into status.json for OAuth2 server
- Add docs folder for project documentation

### Changed
- Fix a bug in client to prevent calling oauth2 server multiple times if in renew window.
- Add socket timeout for client
- update client.json in test resource to simulate different errors.

## 0.1.7 - 2016-10-05
### Added
- Introduce MiddlewareHandler interface so that user can plug in more middleware or switch middleware

### Changed
- Fixed info test case to clear the injected config
- All middleware handlers implement MiddlewareHandler interface so that they are loaded from SPI
- Middleware handlers will be enabled by checking isEnable()
- Update validator test case to remove oauth2 dependency
- Fix the NPE issue if swagger specification does not have security defined
- SwaggerHandler will only be enabled if swagger.json exists in config
- Fix the token helper to get token from OAuth2 server

## 0.1.6 - 2016-10-02
### Added
- Add header parameter validation against swagger specification

### Changed
- Refactor validator to fail fast while error occurs
- All validator returns Status object instead


## 0.1.5 - 2016-10-01
### Added
- A body parser handler to parse body into String and attached to the exchange
- A swagger handler to identify operation based on request uri and method and attach to the exchange

### Changed
- Move swagger related classes from utility to swagger module
- Update security module to leverage swagger handler attachment
- Update validator module to leverage swagger handler and body handler attachments
- Server Info handler is not injected in server but is included into swagger specification

## 0.1.4 - 2016-09-29
### Added
- A generic exception handler for runtime exception, ApiException and uncaught exception

### Changed
- Move checked exceptions to exception module from status

## 0.1.3 - 2016-09-28
### Added

### Changed
- Fix a NPE in request validator if query parameter is missing
- Do not validate query parameter if there is none.
- Handle the case that security defintion is empty.


## 0.1.2 - 2016-09-27
### Added
- Jwt token scope verification based on swagger spec in security
- Status module to standardize error response
- Config can be loaded from classpath directly so that test case can inject different combination of configs.

### Changed
- Update the jwt.json and secuirty.json to support multiple certificates and kid to pick up the right certificate
for jwt verification. Also, expired token will throw ExpiredJwtException now.
- Move request uri matching and swagger.json to utility
- Move exceptions to status from utility
- Instead of using Jackson ObjectMapper to serialize Status object, using toString now. 10 times faster


## 0.1.1 - 2016-09-19
### Added
- Audit
- Client
- Info
- Mask
- Validator



## 0.1.0 - 2016-08-16
### Added
- Server
- Config
- Utilit
- Security






