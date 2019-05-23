# ![LOGO](logo.png) Service Management **flow**ground Connector

## Description

A generated **flow**ground connector for the Service Management API (version v1).

Generated from: https://api.apis.guru/v2/specs/googleapis.com/servicemanagement/v1/swagger.json<br/>
Generated at: 2019-05-23T12:13:38+03:00

## API Description

Google Service Management allows service producers to publish their services on Google Cloud Platform so that they can be discovered and used by service consumers.

## Authorization

Supported authorization schemes:
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### Lists service operations that match the specified filter in the request.

*Tags:* `operations`

#### Input Parameters
* `filter` - _optional_ - A string for filtering Operations.
  The following filter fields are supported&#58;

  * serviceName&#58; Required. Only `=` operator is allowed.
  * startTime&#58; The time this job was started, in ISO 8601 format.
    Allowed operators are `>=`,  `>`, `<=`, and `<`.
  * status&#58; Can be `done`, `in_progress`, or `failed`. Allowed
    operators are `=`, and `!=`.

  Filter expression supports conjunction (AND) and disjunction (OR)
  logical operators. However, the serviceName restriction must be at the
  top-level and can only be combined with other restrictions via the AND
  logical operator.

  Examples&#58;

  * `serviceName={some-service}.googleapis.com`
  * `serviceName={some-service}.googleapis.com AND startTime>="2017-02-01"`
  * `serviceName={some-service}.googleapis.com AND status=done`
  * `serviceName={some-service}.googleapis.com AND (status=done OR startTime>="2017-02-01")`
* `name` - _optional_ - Not used.
* `pageSize` - _optional_ - The maximum number of operations to return. If unspecified, defaults to
50. The maximum value is 100.
* `pageToken` - _optional_ - The standard list page token.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Lists managed services.<br/>
> <br/>
> Returns all public services. For authenticated users, also returns all<br/>
> services the calling user has "servicemanagement.services.get" permission<br/>
> for.<br/>
> <br/>
> **BETA:** If the caller specifies the `consumer_id`, it returns only the<br/>
> services enabled on the consumer. The `consumer_id` must have the format<br/>
> of "project:{PROJECT-ID}".

*Tags:* `services`

#### Input Parameters
* `consumerId` - _optional_ - Include services consumed by the specified consumer.

The Google Service Management implementation accepts the following
forms:
- project:<project_id>
* `pageSize` - _optional_ - The max number of items to include in the response list. Page size is 50
if not specified. Maximum value is 100.
* `pageToken` - _optional_ - Token identifying which result to start with; returned by a previous list
call.
* `producerProjectId` - _optional_ - Include services produced by the specified project.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Creates a new managed service.<br/>
> Please note one producer project can own no more than 20 services.<br/>
> <br/>
> Operation<response: ManagedService>

*Tags:* `services`

#### Input Parameters
* `$.xgafv` - _optional_ - V1 error format.
    Possible values: 1, 2.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Deletes a managed service. This method will change the service to the<br/>
> `Soft-Delete` state for 30 days. Within this period, service producers may<br/>
> call UndeleteService to restore the service.<br/>
> After 30 days, the service will be permanently deleted.<br/>
> <br/>
> Operation<response: google.protobuf.Empty>

*Tags:* `services`

#### Input Parameters
* `serviceName` - _required_ - The name of the service.  See the [overview](/service-management/overview)
for naming requirements.  For example: `example.googleapis.com`.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Gets a managed service. Authentication is required unless the service is<br/>
> public.

*Tags:* `services`

#### Input Parameters
* `serviceName` - _required_ - The name of the service.  See the `ServiceManager` overview for naming
requirements.  For example: `example.googleapis.com`.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Gets a service configuration (version) for a managed service.

*Tags:* `services`

#### Input Parameters
* `configId` - _optional_ - The id of the service configuration resource.

This field must be specified for the server to return all fields, including
`SourceInfo`.
* `serviceName` - _required_ - The name of the service.  See the [overview](/service-management/overview)
for naming requirements.  For example: `example.googleapis.com`.
* `view` - _optional_ - Specifies which parts of the Service Config should be returned in the
response.
    Possible values: BASIC, FULL.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Lists the history of the service configuration for a managed service,<br/>
> from the newest to the oldest.

*Tags:* `services`

#### Input Parameters
* `pageSize` - _optional_ - The max number of items to include in the response list. Page size is 50
if not specified. Maximum value is 100.
* `pageToken` - _optional_ - The token of the page to retrieve.
* `serviceName` - _required_ - The name of the service.  See the [overview](/service-management/overview)
for naming requirements.  For example: `example.googleapis.com`.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Creates a new service configuration (version) for a managed service.<br/>
> This method only stores the service configuration. To roll out the service<br/>
> configuration to backend systems please call<br/>
> CreateServiceRollout.<br/>
> <br/>
> Only the 100 most recent service configurations and ones referenced by<br/>
> existing rollouts are kept for each service. The rest will be deleted<br/>
> eventually.

*Tags:* `services`

#### Input Parameters
* `serviceName` - _required_ - The name of the service.  See the [overview](/service-management/overview)
for naming requirements.  For example: `example.googleapis.com`.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Gets a service configuration (version) for a managed service.

*Tags:* `services`

#### Input Parameters
* `configId` - _required_ - The id of the service configuration resource.

This field must be specified for the server to return all fields, including
`SourceInfo`.
* `serviceName` - _required_ - The name of the service.  See the [overview](/service-management/overview)
for naming requirements.  For example: `example.googleapis.com`.
* `view` - _optional_ - Specifies which parts of the Service Config should be returned in the
response.
    Possible values: BASIC, FULL.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Creates a new service configuration (version) for a managed service based<br/>
> on<br/>
> user-supplied configuration source files (for example: OpenAPI<br/>
> Specification). This method stores the source configurations as well as the<br/>
> generated service configuration. To rollout the service configuration to<br/>
> other services,<br/>
> please call CreateServiceRollout.<br/>
> <br/>
> Only the 100 most recent configuration sources and ones referenced by<br/>
> existing service configurtions are kept for each service. The rest will be<br/>
> deleted eventually.<br/>
> <br/>
> Operation<response: SubmitConfigSourceResponse>

*Tags:* `services`

#### Input Parameters
* `serviceName` - _required_ - The name of the service.  See the [overview](/service-management/overview)
for naming requirements.  For example: `example.googleapis.com`.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Lists the history of the service configuration rollouts for a managed<br/>
> service, from the newest to the oldest.

*Tags:* `services`

#### Input Parameters
* `filter` - _optional_ - Use `filter` to return subset of rollouts.
The following filters are supported:
  -- To limit the results to only those in
     [status](google.api.servicemanagement.v1.RolloutStatus) 'SUCCESS',
     use filter='status=SUCCESS'
  -- To limit the results to those in
     [status](google.api.servicemanagement.v1.RolloutStatus) 'CANCELLED'
     or 'FAILED', use filter='status=CANCELLED OR status=FAILED'
* `pageSize` - _optional_ - The max number of items to include in the response list. Page size is 50
if not specified. Maximum value is 100.
* `pageToken` - _optional_ - The token of the page to retrieve.
* `serviceName` - _required_ - The name of the service.  See the [overview](/service-management/overview)
for naming requirements.  For example: `example.googleapis.com`.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Creates a new service configuration rollout. Based on rollout, the<br/>
> Google Service Management will roll out the service configurations to<br/>
> different backend services. For example, the logging configuration will be<br/>
> pushed to Google Cloud Logging.<br/>
> <br/>
> Please note that any previous pending and running Rollouts and associated<br/>
> Operations will be automatically cancelled so that the latest Rollout will<br/>
> not be blocked by previous Rollouts.<br/>
> <br/>
> Only the 100 most recent (in any state) and the last 10 successful (if not<br/>
> already part of the set of 100 most recent) rollouts are kept for each<br/>
> service. The rest will be deleted eventually.<br/>
> <br/>
> Operation<response: Rollout>

*Tags:* `services`

#### Input Parameters
* `serviceName` - _required_ - The name of the service.  See the [overview](/service-management/overview)
for naming requirements.  For example: `example.googleapis.com`.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Gets a service configuration rollout.

*Tags:* `services`

#### Input Parameters
* `rolloutId` - _required_ - The id of the rollout resource.
* `serviceName` - _required_ - The name of the service.  See the [overview](/service-management/overview)
for naming requirements.  For example: `example.googleapis.com`.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Disables a service for a project, so it can no longer be<br/>
> be used for the project. It prevents accidental usage that may cause<br/>
> unexpected billing charges or security leaks.<br/>
> <br/>
> Operation<response: DisableServiceResponse>

*Tags:* `services`

#### Input Parameters
* `serviceName` - _required_ - Name of the service to disable. Specifying an unknown service name
will cause the request to fail.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Enables a service for a project, so it can be used<br/>
> for the project. See<br/>
> [Cloud Auth Guide](https://cloud.google.com/docs/authentication) for<br/>
> more information.<br/>
> <br/>
> Operation<response: EnableServiceResponse>

*Tags:* `services`

#### Input Parameters
* `serviceName` - _required_ - Name of the service to enable. Specifying an unknown service name will
cause the request to fail.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Revives a previously deleted managed service. The method restores the<br/>
> service using the configuration at the time the service was deleted.<br/>
> The target service must exist and must have been deleted within the<br/>
> last 30 days.<br/>
> <br/>
> Operation<response: UndeleteServiceResponse>

*Tags:* `services`

#### Input Parameters
* `serviceName` - _required_ - The name of the service. See the [overview](/service-management/overview)
for naming requirements. For example: `example.googleapis.com`.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Generates and returns a report (errors, warnings and changes from<br/>
> existing configurations) associated with<br/>
> GenerateConfigReportRequest.new_value<br/>
> <br/>
> If GenerateConfigReportRequest.old_value is specified,<br/>
> GenerateConfigReportRequest will contain a single ChangeReport based on the<br/>
> comparison between GenerateConfigReportRequest.new_value and<br/>
> GenerateConfigReportRequest.old_value.<br/>
> If GenerateConfigReportRequest.old_value is not specified, this method<br/>
> will compare GenerateConfigReportRequest.new_value with the last pushed<br/>
> service configuration.

*Tags:* `services`

#### Input Parameters
* `$.xgafv` - _optional_ - V1 error format.
    Possible values: 1, 2.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Gets the latest state of a long-running operation.  Clients can use this<br/>
> method to poll the operation result at intervals as recommended by the API<br/>
> service.

*Tags:* `operations`

#### Input Parameters
* `name` - _required_ - The name of the operation resource.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Gets the access control policy for a resource.<br/>
> Returns an empty policy if the resource exists and does not have a policy<br/>
> set.

*Tags:* `services`

#### Input Parameters
* `resource` - _required_ - REQUIRED: The resource for which the policy is being requested.
See the operation documentation for the appropriate value for this field.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Sets the access control policy on the specified resource. Replaces any<br/>
> existing policy.

*Tags:* `services`

#### Input Parameters
* `resource` - _required_ - REQUIRED: The resource for which the policy is being specified.
See the operation documentation for the appropriate value for this field.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Returns permissions that a caller has on the specified resource.<br/>
> If the resource does not exist, this will return an empty set of<br/>
> permissions, not a NOT_FOUND error.<br/>
> <br/>
> Note: This operation is designed to be used for building permission-aware<br/>
> UIs and command-line tools, not for authorization checking. This operation<br/>
> may "fail open" without warning.

*Tags:* `services`

#### Input Parameters
* `resource` - _required_ - REQUIRED: The resource for which the policy detail is being requested.
See the operation documentation for the appropriate value for this field.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

## License

**flow**ground :- Telekom iPaaS / googleapis-com-servicemanagement-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
