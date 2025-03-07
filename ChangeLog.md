# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased]

## [1.7.0] - 2021-06-18

### API changes list

- Add the PreSendingAdvice to AOP.

- Make Json::Value as a SQL parameters type.

- Add the int type for the Row index parameter.

- Add SSL_CONF_cmd support.

- Add the setCustomStatusCode method.

### Changes

- Fix sync_wait/co_future use-after-free.

- Add the AccessLogger plugin.

- Make AsyncTask only destruct when the coroutine reaches end of executions.

- Add Drogon test framework.

- Improve WebSocket mask handling.

- Add minimal server side examples.

- Optimize HttpControllersRouter for cases where regex is not needed.

- Create controller instances after running instead of after being called.

### Fixed

- Move resolverPtr when destroying an HttpClientImpl object.

- Modify the way to create sqlite3 client.

- Fix a bug when a network failure occurs on Redis connections.

- Fix a bug of string_view for MSVC.

- Fix 'build.sh -tshared'.

- Fix compiler warnings.

- Fix CacheMap crash in CI tests.

## [1.6.0] - 2021-05-15

### API changes list

- Add option to set default handler.

- Add the setTimeout() method to the DbClient class and the RedisClient class.

- Add the validateCert parameter to the newWebSocketClient method.

### Changed

- A few mini changes to drogon_ctl command.

- Improve the MultiPartParser class.

- Add GNU -Werror & fix warnings.

- Enhancements on files part.

- Add version/soversion to shared library.

- Disallow coroutines to be resolved as plain subroutine handlers.

- Send the content-length header even if the body(POST,PUT,OPTIONS,PATCH) is empty.

- Use make_exception_ptr instead of throw/catch when possible.

- Remove duplicated inclusion.

- Print error before terminating in AsyncTask.

- Allow users to override drogon Find modules.

- Use two-phase construction for the DbClientImpl and the RedisClientImpl.

- Add support 'select <db>' for redis.

### Fixed

- Fix a bug of the Transaction class.

- Copy CoroMapper.h to installation location.

- Remove the related request from the buffer if it's not sent after the timeout.

- Fix ORM with SQLite3 not compiling on Arch Linux.

- Fix an error when constructing RedisClientImpl objects.

- Fix coroutine frame leak upon assigning to awaitable.

- Set running flag to true before installing plugins.

- Fix double free in coroutine exception handling.

## [1.5.1] - 2021-04-10

### Fixed

- Fix a bug of reflection failure.

## [1.5.0] - 2021-04-10

### API changes list

- Add option to disable signal handling.

- Added newFileResponse Support for buffers in memory.

- Add a method to HttpRequest to set the user_agent header.

- Catch exceptions thrown by handlers.

### Changed

- Add convert method to models.

- Add Arch Dockerfile.

- Add Redis support.

- Print error and exit when IP parsing failed in server startup.

- Use a canonical way of calling max() function on Windows.

- Remove an assertion statement in the HttpClientImpl class.

- Send ping messages by default for WebSockets.

- Use canonical cmake logic for cross-compilation.

- set make job count to the number of threads in GitHub Actions workflow.

- Use lambda instead of std::bind in HttpServer.

- Add exports macro to allow Shared Library with hidden symbols by default.

- Remove repeated class names on relationships from the model generator.

### Fixed

- Fix compile warnings in SQL client.

- Fix compilation errors for the TimeFilter example.

- Fix build.sh missing nproc error in build for macOS.

- Fix a bug when creating sqlite3 models.

- Fix two building corner cases, CMake quality of life improvements.

- Add CoroMapper to models' friends.

## [1.4.1] - 2021-03-07

### Fixed

- Fix a bug of DbClientImpl class that can lead to a crash when database connections are breaking.

## [1.4.0] - 2021-03-05

### API changes list

- Add coroutine support.

- Add default value interface to SqlBinder for MySQL and PostgreSQL.

- Support SNI in the HttpClient class.

- Validate certificate in HttpClient.

- HttpRequest: add a feature to avoid URL encoding of the path.

### Changed

- Handle cross-compiling properly.

- Lowercase all HTTP headers, add webp and avif types.

- Modify FindMySQL.cmake

### Fixed

- Fix an error in the HttpClient class when a response has no content-length.

- Return 404 or 405 responses correctly.

- Fix compilation errors on vs2019.

- Fix stack use after scope error in client_example.

- Fix the error when the SSL handshake fails.

## [1.3.0] - 2021-01-16

### API changes list

- Add an option for setting float precision in Json string.

### Fixed

- Fix brotli link order.

- Fix cmake with drogonctl cross-compilation.

- sqlite3: Insert into stmtsMap_ as string_view.

- Fix some bugs when creating models via drogon_ctl.

- Fix an error in sqlite3 ORM generator.

- Fix an error with missing composite key to sqlite3 ORM generator.

### Changed

- Remove the use of std::filesystem to adapt to old compilers.

- Add github actions.

- Serve wasm files with the correct MIME type.

## [1.2.0] - 2020-12-12

### Fixed

- Fix error when receiving response without content-length header.

- Fix a stack-overflow error when high concurrency happening on sqlite3.

- Fix MinGW ORM building by enabling htonll and ntohll.

### Changed

- Modify the WebSocketTest controller to create a simple chat room.

- Add support for OpenBSD.

- Return 400 if the content-length is invalid.

- Don't send content type in a 304 response.

- Add the reuse_port option to app() interface.

- Add the 'std::optional' support in the SqlBinder class and the Session class.

- Add implicit page resolving capability.

## [1.1.0] - 2020-10-31

### Fixed

- Fix failing to connect to DB if parameters contains spaces.

- Fix a CMAKE bug when SHARED and EXAMPLES are on.

- Fix the HttpServer::isWebSocket method.

- Find MariaDB client library correctly on Ubuntu 20.04.

- Fix a bug when creating sqlite3 database models.

- Fix a bug in the Mapper::insertFuture method.

### Changed

- Disable TLS1.0/1.1 on HTTPS by default.

- Use explicit lambda capture lists.

- Modify the procedure of the app().run() method.

- Support namespaces when creating view source files.

- Add --path-to-namespace option to drogon_ctl for creating views.

- Add the Host and Sec-WebSocket-Version headers when connecting to a websocket server.

## [1.0.0] - 2020-09-27

### Fixed

- Fix an issue of simple_reverse_proxy when handling chunked transfer-encoding.

- Fix a bug when losting connection to MySQL server during query.

- Remove the expired std::iterator template.

- Fix a bug when creating models in some special cases.

### API changes list

- Modify methods related to headers.

- Remove the expired std::iterator template.

- Add getListeners() method to the HttpAppFramework class.

- Remove the useless method stat() from the PluginBase class.

- Add ConfigLoader::ConfigLoader(const Json::Value &data).

### Changed

- Add support for status code 418.

- Modify session handling.

- Modify the FileUpload.csp in simple_example to avoid CORS.

- remove execution permission on /tmp/drogon.lock.

## [1.0.0-beta21] - 2020-08-19

### Changed

- Modify the Result class in ORM.

### Fixed

- Fix zlib link error on Windows for the latest vcpkg.

## [1.0.0-beta20] - 2020-08-15

### API changes list

- Provide users with a method to change the session ID of a session.

### Changed

- Modify parseContentType function.

- Modify the docker file to build release version in docker.

- Set session to requests for websockets.

- Modify parseContentType function.

- Change the return value type of the mktime() function in models.

- Fix compilation warning of sprintf function.

### Fixed

- Fix a bug when saving uploaded files on Windows.

- Fix a MySQL issue when connections are lost.

- Resolve an issue when sending big files (>=2GB) on Windows.

- Fix boost::string_view compilation error of MysqlConnection class.

- Set the response Access-Control-Allow-Headers header correctly for CORS.

- Fix a bug in drogon_ctl when creating a model, that causes to write source files multiple times.

## [1.0.0-beta19] - 2020-07-16

### API changes list

- Add a method to disable unicode escaping in json string.

- Add a timeout parameter when sending HTTP requests.

- Add the getJsonError method.

### Changed

- Remove the restriction on the location of layout tags in views.

- Add a way to set the character set when creating DbClient objects.

- Make `GET` as the only method for accessing static files.

- Modify the 404 pages generator.

- Modify the DbClient class.

- Optimize the HttpResponse class.

### Fixed

- Properly handle chunked encoding requests.

- Destroy DNS resolver of HttpClient in the correct thread.

- Add the header <cctype> to resolve build errors in VS2017.

## [1.0.0-beta18] - 2020-06-14

### API changes list

- Add a new joinpoint of AOP for modification on each HTTP response.

- Add a method for the TERM signal handling.

- Add getContextRef method to the WebSocketConnection class.

### Changed

- Create a class template for publish subscribe pattern.

- Add contribution recommendations.

- Send a close message when closing a web socket connection.

- Add additional formats for getHttpDate function.

- Make app().run() method callable on a non-main thread.

- Add digest filter in examples.

- Use string_view to parse multipart/form-data requests.

### Fixed

- Fix building of ORM on FreeBSD.

- Fix a Mysql connection error on Windows.

- Fix a bug in ListenerManager::getIOLoop().

- Fix the count() method of Mysql ORM.

- Fix a compilation issue on windows.

- Fix model generation for PostgreSQL primary keys.

- Fix a bug with quoted column names in sqlite3 databases.

## [1.0.0-beta17] - 2020-05-22

### API changes list

- Add methods to get DbClient connection status

### Changed

- Add causal profiling with coz

- Add filters on static file locations

- Pass data from view to its layout container

- Add additional HttpStatusCodes and implement a custom error handler

- Modify drogon_ctl to show more compilation information

### Fixed

- Fix a bug in drogon_ctl (when size of a line is larger than buffer size)

- Fix a connection bug of MariaDB clients

## [1.0.0-beta16] - 2020-04-27

### API changes list

- Standardize Row and Result api in ORM

### Changed

- Add support for brotli compression

- Parse content-type of HTTP requests

- Remove non standard macros

- Support url safe base64 codec

## [1.0.0-beta15] - 2020-03-28

### API changes list

- Modify the Attributes interface of the HttpRequest class

- Add the getHomePage() method to HttpAppFramework

### Changed

- Support br compression files

- Update Content-Type support for PDF

- Add support for MSVC 2015

- Optimize the rendering of HTTP responses

- Update the Dynamic Views Loading, add the `layout` tag

- Graceful shutdown

### Fixed

- Fix error when finding the jsoncpp library

- Fix the 'many to many' relationship in ORM

- Fix a bug when creating json responses

- Fix a bug on filters with WebSocketControllers

- Fix a fatal bug in the MysqlConnection class

- Fix crash with partial matched url

- Fix null jsonObject from newHttpJsonRequest

## [1.0.0-beta14] - 2020-02-17

### API changes list

- None

### Added

- Add IOLoop access function

### Changed

- Add support for regular expressions when routing

- Add location configuration for static resources

- Port drogon to Windows

- Support 'password' keyword in configuration files

- Remove get_version.sh

- Modify dynamic view loading algorithm, add 'layout' tag for view generation.

### Fixed

- Fix an issue of out-of-range (#334)

- Fix a bug in views generation (#341)

## [1.0.0-beta13] - 2020-01-04

### API changes list

- None

### Changed

- Add some unit tests (based on gtest)

- Add a reverse proxy example

- Make a patch to support the ossp UUID library

- Make shared linking possible

- Add the drogon::OStringStream class

- Optimize ORM

- Modify singleton logic of DrClassMap

### Fixed

- Fix an error in the batch mode of libpq

- Fix an error when clients use HTTP1.0

## [1.0.0-beta12] - 2019-11-30

### Changed

- Make dg_ctl a symlink

- Modify some code styles

- Explicitly set path to '/' for JSESSIONID cookie

- Handle gzip errors safely

- Add the SecureSSLRedirector plugin

### Fixed

- Fix a bug in dg_ctl for creating models of sqlite3

- Reset the flag used to parse json to false before recycling HttpRequest objects

## [1.0.0-beta11] - 2019-11-06

### Changed

- Delete useless log output

## [1.0.0-beta10] - 2019-11-04

### API changes list

- None

### Changed

- Add the headers configuration option for static files

### Fixed

- Fix(compilation on alpine): Replace u_short alias.


## [1.0.0-beta9] - 2019-10-28

### API changes list

- Add interfaces for accessing content of attachments.

- Add option to disable setting the 404 status code of the custom 404 page.

- Make user can use any string as a placeholder's name in routing patterns.

- Add type conversion methods to the HttpRequest and HttpResponse classes.

### Changed

- Modify cmake configuration.

- Modify the quit() method.

- Implement relationships in ORM.

### Fixed

- Fix size_t underflow of drogon_ctl.

- Fix some race conditions.

- Fix a busy loop bug when connections to MySQL server are timeout.


## [1.0.0-beta8] - 2019-10-03

### API changes list

- Add length() method to the Field class.

- Add `as<bool>()` function template specialization to the Field class.

- Add add attribute store methods to the HttpRequest class.

- Add the setCustomContentTypeString() method to the HttpRequest class.

- Add thread storage.


### Changed

- Use .find('x') instead of .find("x") in a string search.

- Add the ability to create restful API controllers.

### Fixed

- Fix a bug of creating models for MySQL.

- Fix a bug when HTTP method is PUT.

- Fix a bug when using 'is null' substatement in ORM.

- Fix a sqlite3 bug when some SQL errors occur.

- Fix bug with parsing json.

- Fix url decode.

- Fix a error in HttpClient.

- Fix a error in setThreadNum method.

- Fix some race conditions.

## [1.0.0-beta7] - 2019-08-31

### API changes list

- Remove the default value parameter of some methods (#220)

### Changed

- Optimize DNS in HttpClient and WebSocketClient (support c-ares library).

- Reduce dependencies between declarations.

- Add database tests in the travis CI and add test cases to database tests.

- Reduce size of docker image.

- Make the framework API support chained calls.
  
- Add a synchronous join point for AOP.

- Modify the CMakeLists to modern cmake style.

### Fixed

- Fix bugs in default return values of functions(#220),

- Fix a bug in the cmake configuration file when there's '+' in the building path.

- Fix a bug in drogon_ctl (when creating orm models)


## [1.0.0-beta6] - 2019-08-08

### API changes list

- None

### Changed

- Modify the 'create view' sub-command of drogon_ctl

- Optimize the transmission of pipelining responses.

- Add the DrogonConfig.cmake file so that users can use drogon with the `find_package(Drogon)` command.

## [1.0.0-beta5] - 2019-08-01

### API changes list

- None

### Added

- Add two methods to control if the Server header or the Date header is sent to clients with HTTP responses.
  * void HttpAppFramework::enableServerHeader(bool);
  * void HttpAppFramework::enableDateHeader(bool);

### Changed

- Support high performance batch mode of libpq.

### Fixed

- None

## [1.0.0-beta4] - 2019-07-30

### API changes list

- HttpRequest::query() returns a const reference of std::string instead of a string_view
- WebSocketConnection::setContext(), WebSocketConnection::getContext(), etc.
- Remove the config.h from public API.

### Added

- None

### Changed

- Modify the CMakeLists.txt
- Modify the get_version.sh

### Fixed

- None

## [1.0.0-beta3] - 2019-07-28

### API changes list

- None

### Added

- Add a README file for examples.
- Add some managers to reduce the size of the HttpAppFrameworkImpl code.
- Add missing wasm ContentType.

### Changed

- Update the submodule - trantor.
- Optimize processing of HTTP pipelining.

### Fixed

- Fix an error in the HttpClient class when sending a request using the HEAD method.

## [1.0.0-beta2] - 2019-07-10

### API changes list

- Add setBody methods to the HttpRequest class.
- Add the setContentTypeCodeAndCustomString method to the HttpResponse class.

### Added

- Add stress testing command to drogon_ctl.
- Add -v, -h parameters to drogon_ctl.

### Changed

- Update the submodule - trantor.
- Modify the handling of CORS.
- Optimize the htmlTranslate method and the Field class.
- Make all listeners share IO threads in the MacOS/Unix system.

### Fixed

- Fix a bug of the IsPlugin class.
- Use default constructor of string_view to reset _statusMessage to fix a warning on GCC 9.1 on Arch Linux.

## [1.0.0-beta1] - 2019-06-11

[Unreleased]: https://github.com/an-tao/drogon/compare/v1.7.0...HEAD

[1.7.0]: https://github.com/an-tao/drogon/compare/v1.6.0...v1.7.0

[1.6.0]: https://github.com/an-tao/drogon/compare/v1.5.1...v1.6.0

[1.5.1]: https://github.com/an-tao/drogon/compare/v1.5.0...v1.5.1

[1.5.0]: https://github.com/an-tao/drogon/compare/v1.4.1...v1.5.0

[1.4.1]: https://github.com/an-tao/drogon/compare/v1.4.0...v1.4.1

[1.4.0]: https://github.com/an-tao/drogon/compare/v1.3.0...v1.4.0

[1.3.0]: https://github.com/an-tao/drogon/compare/v1.2.0...v1.3.0

[1.2.0]: https://github.com/an-tao/drogon/compare/v1.1.0...v1.2.0

[1.1.0]: https://github.com/an-tao/drogon/compare/v1.0.0...v1.1.0

[1.0.0]: https://github.com/an-tao/drogon/compare/v1.0.0-beta21...v1.0.0

[1.0.0-beta21]: https://github.com/an-tao/drogon/compare/v1.0.0-beta20...v1.0.0-beta21

[1.0.0-beta20]: https://github.com/an-tao/drogon/compare/v1.0.0-beta19...v1.0.0-beta20

[1.0.0-beta19]: https://github.com/an-tao/drogon/compare/v1.0.0-beta18...v1.0.0-beta19

[1.0.0-beta18]: https://github.com/an-tao/drogon/compare/v1.0.0-beta17...v1.0.0-beta18

[1.0.0-beta17]: https://github.com/an-tao/drogon/compare/v1.0.0-beta16...v1.0.0-beta17

[1.0.0-beta16]: https://github.com/an-tao/drogon/compare/v1.0.0-beta15...v1.0.0-beta16

[1.0.0-beta15]: https://github.com/an-tao/drogon/compare/v1.0.0-beta14...v1.0.0-beta15

[1.0.0-beta14]: https://github.com/an-tao/drogon/compare/v1.0.0-beta13...v1.0.0-beta14

[1.0.0-beta13]: https://github.com/an-tao/drogon/compare/v1.0.0-beta12...v1.0.0-beta13

[1.0.0-beta12]: https://github.com/an-tao/drogon/compare/v1.0.0-beta11...v1.0.0-beta12

[1.0.0-beta11]: https://github.com/an-tao/drogon/compare/v1.0.0-beta10...v1.0.0-beta11

[1.0.0-beta10]: https://github.com/an-tao/drogon/compare/v1.0.0-beta9...v1.0.0-beta10

[1.0.0-beta9]: https://github.com/an-tao/drogon/compare/v1.0.0-beta8...v1.0.0-beta9

[1.0.0-beta8]: https://github.com/an-tao/drogon/compare/v1.0.0-beta7...v1.0.0-beta8

[1.0.0-beta7]: https://github.com/an-tao/drogon/compare/v1.0.0-beta6...v1.0.0-beta7

[1.0.0-beta6]: https://github.com/an-tao/drogon/compare/v1.0.0-beta5...v1.0.0-beta6

[1.0.0-beta5]: https://github.com/an-tao/drogon/compare/v1.0.0-beta4...v1.0.0-beta5

[1.0.0-beta4]: https://github.com/an-tao/drogon/compare/v1.0.0-beta3...v1.0.0-beta4

[1.0.0-beta3]: https://github.com/an-tao/drogon/compare/v1.0.0-beta2...v1.0.0-beta3

[1.0.0-beta2]: https://github.com/an-tao/drogon/compare/v1.0.0-beta1...v1.0.0-beta2

[1.0.0-beta1]: https://github.com/an-tao/drogon/releases/tag/v1.0.0-beta1
