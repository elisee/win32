---
title: The Need For Extended Error Information
description: A primary difficulty associated with troubleshooting RPC problems is mapping an RPC error code to the underlying problem.
ms.assetid: 'aef3bcd6-ecaa-4639-b765-da90db6ddf82'
---

# The Need For Extended Error Information

A primary difficulty associated with troubleshooting RPC problems is mapping an RPC error code to the underlying problem. A configuration error or networking problem can result in one or more workstations receiving RPC\_S\_\* errors, but that workstation can only display the error, paraphrase it, or save it to some log file. Whichever approach is used, the person troubleshooting the problem is deprived of essential information:

-   Where the error occurred. It may have occurred on the local computer, on a remote computer called by the local computer, or on a remote computer called by another remote computer.
-   The original error code that caused the problem. To conform to the OSF standard, MS RPC maps error codes to RPC\_S\_\* codes. RPC\_S\_\* codes are too generic, however, and offer little useful troubleshooting information.
-   Any context information related to the occurrence of the problem. With non-RPC errors, debuggers can stop the process and examine the context in which the error occurred. RPC errors are often generated by a remote process or computer, which continues processing after returning the error, and overwrites any context pertaining to the error.

 

 



