<!--
 Licensed to the Apache Software Foundation (ASF) under one
 or more contributor license agreements.  See the NOTICE file
 distributed with this work for additional information
 regarding copyright ownership.  The ASF licenses this file
 to you under the Apache License, Version 2.0 (the
 "License"); you may not use this file except in compliance
 with the License.  You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

 Unless required by applicable law or agreed to in writing,
 software distributed under the License is distributed on an
 "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
 KIND, either express or implied.  See the License for the
 specific language governing permissions and limitations
 under the License.
 -->

# \DAGRunApi

All URIs are relative to *http://localhost/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**DeleteDagRun**](DAGRunApi.md#DeleteDagRun) | **Delete** /dags/{dag_id}/dagRuns/{dag_run_id} | Delete a DAG Run
[**GetDagRun**](DAGRunApi.md#GetDagRun) | **Get** /dags/{dag_id}/dagRuns/{dag_run_id} | Get a DAG Run
[**GetDagRuns**](DAGRunApi.md#GetDagRuns) | **Get** /dags/{dag_id}/dagRuns | Get all DAG Runs
[**GetDagRunsBatch**](DAGRunApi.md#GetDagRunsBatch) | **Post** /dags/~/dagRuns/list | Get all DAG Runs from aall DAGs.
[**PostDagRun**](DAGRunApi.md#PostDagRun) | **Post** /dags/{dag_id}/dagRuns/{dag_run_id} | Trigger a DAG Run



## DeleteDagRun

> DeleteDagRun(ctx, dagId, dagRunId)

Delete a DAG Run

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**dagId** | **string**| The DAG ID. | 
**dagRunId** | **string**| The DAG Run ID. | 

### Return type

 (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetDagRun

> DagRun GetDagRun(ctx, dagId, dagRunId)

Get a DAG Run

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**dagId** | **string**| The DAG ID. | 
**dagRunId** | **string**| The DAG Run ID. | 

### Return type

[**DagRun**](DAGRun.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetDagRuns

> DagRunCollection GetDagRuns(ctx, dagId, optional)

Get all DAG Runs

This endpoint allows specifying `~` as the dag_id to retrieve DAG Runs for all DAGs. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**dagId** | **string**| The DAG ID. | 
 **optional** | ***GetDagRunsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetDagRunsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **limit** | **optional.Int32**| The numbers of items to return. | [default to 100]
 **offset** | **optional.Int32**| The number of items to skip before starting to collect the result set. | 
 **executionDateGte** | **optional.Time**| Returns objects greater or equal to the specified date. This can be combined with execution_date_lte parameter to receive only the selected period.  | 
 **executionDateLte** | **optional.Time**| Returns objects less than or equal to the specified date. This can be combined with execution_date_gte parameter to receive only the selected period.  | 
 **startDateGte** | **optional.Time**| Returns objects greater or equal the specified date. This can be combined with startd_ate_lte parameter to receive only the selected period.  | 
 **startDateLte** | **optional.Time**| Returns objects less or equal the specified date. This can be combined with start_date_gte parameter to receive only the selected period.  | 
 **endDateGte** | **optional.Time**| Returns objects greater or equal the specified date. This can be combined with start_date_lte parameter to receive only the selected period.  | 
 **endDateLte** | **optional.Time**| Returns objects less than or equal to the specified date. This can be combined with start_date_gte parameter to receive only the selected period.  | 

### Return type

[**DagRunCollection**](DAGRunCollection.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetDagRunsBatch

> DagRunCollection GetDagRunsBatch(ctx, listDagRunsForm)

Get all DAG Runs from aall DAGs.

This endpoint is a POST to allow filtering across a large number of DAG IDs, where as a GET it would run in to maximum HTTP request URL lengthlimits 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**listDagRunsForm** | [**ListDagRunsForm**](ListDagRunsForm.md)|  | 

### Return type

[**DagRunCollection**](DAGRunCollection.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## PostDagRun

> DagRun PostDagRun(ctx, dagId, dagRunId, dagRun)

Trigger a DAG Run

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**dagId** | **string**| The DAG ID. | 
**dagRunId** | **string**| The DAG Run ID. | 
**dagRun** | [**DagRun**](DagRun.md)|  | 

### Return type

[**DagRun**](DAGRun.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

