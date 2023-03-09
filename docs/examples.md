---
title: "Examples"
nav_order: 3
---

# DLL embed in the application

```C#
static string TestRunSDDP(string case_name, string updatefilename)
{
  RequestRunCase request = new RequestRunCase();
  request.casename = case_name;
  request.model = "sddp";
  request.updatefilename = updatefilename;
  ResponseRunCase response = GetResponse<ResponseRunCase>(request.run());
  if (response != null)
    return response.run_id;
  return null;
}
```

```C#
static string TestRunNCP(string case_name, string updatefilename)
{
  RequestRunCase request = new RequestRunCase();
  request.casename = case_name;
  request.model = "ncp";
  request.updatefilename = updatefilename;
  ResponseRunCase response = GetResponse<ResponseRunCase>(request.run());
  if (response != null)
    return response.run_id;
  return null;
}
```

```C#
static void TestCopyCase(string case_name, string new_case_name, string updatefilename)
{
  RequestCopyCase request = new RequestCopyCase();
  request.casename = case_name;
  request.newcasename = new_case_name;
  request.updatefilename = updatefilename;
  ResponseCopyCase response = GetResponse<ResponseCopyCase>(request.run());
}
```
