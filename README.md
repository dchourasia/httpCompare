Robot Framework - HTTPCompare
==========================

Introduction
------------
This keyword lets you compare two HTTP Requests, given that both the requests are made using 'Make HTTP Request' keyword:
* This enables comparison of JSON response bodies and status codes as of now.
* It will log the difference between response bodies and status codes in robot report and pass/fail the testcase accordingly. 
* Difference between both the responses is termed as Divergence.
    * Actual Divergence (difference between the two responses)
    * Expected Divergence (difference which is acknowledgeably expected by user, should be supplied by the user while invoking this keyword)
* This keyword will compare the actual divergence and expected divergence and will pass if they match, otherwise will highlight the differences and fail.


![License](https://img.shields.io/pypi/l/robotframework.svg)

Prerequisites
-------------
HTTPCompare Library has following prerequisites:
```
robotframework>=3.1.2
jsonpath-ng>=1.4.3
setuptools>=39.1.0
```
you can install all the prerequisites either one by one or using the requirements.txt provided with source code:
```
pip install -r requirements.txt
```
Installation
------------
HTTPCompare Library can be easily installed using pip with following command:
```
pip install robotframework-httpcompare
```
Alternatively it can also be installed from the sourcecode:
```
python setup.py install
```

Compare HTTP Requests
-----------------
**Compare HTTP Requests** is the main keyword of RESTLibrary, it has all the possible parameters which are needed for making any HTTP/REST request along with other parameters needed for various facets of REST API Automation.
 ### Parameters:
 **requestId_1** : request id of first request

 **requestId_2** : request id of second request

 **expectedDivergence** : difference between the two responses, which is acknowledgeably expected by user, should be provided in the format of actual divergence which is logged in robot report. Only difference is that it has expected_<x> node rather than actual_<x> nodes.

 **ignoreNodes** : a list of json-paths of the nodes which we want to be ignored while response body comparison

 **responseComparisonScheme** : this parameter is useful to specify how we want our response bodies to get compared. In case of not sorted comparison, where we want to skip the sequence and verify the arrays with items in random order
                                example : [{"path":"$.items","type":"NotSorted","key":"name"},{"path":"$.items[*].links","type":"NotSorted","key":"rel"}]

  **responseComparisonType** :  type of baseline verification required, default is FULL, other supported values are PARTIAL.

  **responseNames** : using this parameter we can respectively attach nomenclature to the requests provided for comparison, ex responseNames=['elasticsearch response', 'lambda response']


Contributions:
--------------
Creator and maintainer : [Deepak Chourasia](https://www.linkedin.com/in/deepak-chourasia-10767610/)

License
--------
HTTPCompare Library is open source software provided under the [Apache License 2.0](http://apache.org/licenses/LICENSE-2.0)