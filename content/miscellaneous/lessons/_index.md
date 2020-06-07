+++
title = "Lessons"
date = 2020-06-07T16:50:04+02:00
draft = true
+++

## Dictionary 

`TryGetValue()` instead of `contains`. Ex: `TryGetValue("key", out var Variable)`

**Liversage:**
You should gracefully handle the case where mediaType is not in the dictionary and throw an `ArgumentException` like the old code did.
Notice that it is better to use `TryGetValue()` instead of first using `ContainsKey()` and then getting the item using the `this[]` indexer which is what the old code did.

## xUnit.net

Our test cases ran in parallel and running test cases in parallel can cause some problems. Due to the fact the `TestPlayerSpecimen` is used in multiple test cases where session and access tokens are requested, since these are unique and time sensitive you cannot have test that use the `TestPlayerSpecimen` run in parallel. Solution was to put all test cases that use `TestPlayerSpecimen` in a `Test Collection`, which means they will not be executed in parallel, but in sequence. 

[Running Tests in Parallel](https://xunit.github.io/docs/running-tests-in-parallel)

## Struct vs Class

In C# programming, the struct keyword is used to define a value type, while the class keyword is used to define a reference type.

[The 10 Most Common Mistakes in C# Programming](https://www.toptal.com/c-sharp/top-10-mistakes-that-c-sharp-programmers-make)


## Short Circuit Evaluation

[Wikipedia](https://en.wikipedia.org/wiki/Short-circuit_evaluation)

Short circuit evaluation is the way boolean expressions are evaluated in certain programming languages. It is evaluated left to right sequentially, and if the first expression is `false`, the rest is not evaluated if the expression is connected using an `AND` operator. Similarly, if the first expression is true, when it is an `OR` operator, the rest is not evaluated since it is known to be `true`. C# is language which has short circuit evaluation

### C# Example

If the length of the byte array is not atleast 8, then the rest of the expression is not evaluated, and `false` is returned.

```C#
private static bool IsPng(byte[] bytes)
            => bytes.Length >= 8
               && bytes[0] == 0x89
               && bytes[1] == 0x50
               && bytes[2] == 0x4E
               && bytes[3] == 0x47
               && bytes[4] == 0x0D
               && bytes[5] == 0x0A
               && bytes[6] == 0x1A
               && bytes[7] == 0x0A;
```

## [Content Negotiation](https://developer.mozilla.org/en-US/docs/Web/HTTP/Content_negotiation)

Content negotiation is a mechanism for letting the server know what file type is requested by the client. It is done in the `Accept` header. Below is an example, where the `Accept` header holds many different file formats. The `q=0.6` indicates the priority of that file format, if there is no `q`, then the default is `q=1.0`.

```HTTP
GET /images/864?width=360&amp; height=200 HTTP/1.1
Host: localhost:8079
Accept: image/bmp;q=0.7,text/html,application/xhtml+xml,application/xml;q=0.9,image/png;q=0.8,
cache-control: no-cache
Postman-Token: 74da421b-0f77-4320-bef5-93622394d6d3

```

### [Mime Types](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types)

A Multipurpose Internet Mail Extensions (MIME) type is a standard indicating the file format of a file, document, or assortment of bytes.

```
text/plain
text/html
text/javascript
text/css
image/jpeg
image/png
audio/mpeg
audio/ogg
audio/*
video/mp4
application/*
application/json
application/ecmascript
application/octet-stream
```

## Rate Limiting

### Token Bucket Algorithm



## Always put IDs in even the simplest database

Learned when making Valentine day gift, didn't put a ID at first for the love notes, and when I needed to mark the opened ones in the original love note database. I couldn't get a hold on them. So I added ID's to be able to match the opened one in the data base.