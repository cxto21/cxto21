---
title: HTTP Standard Response Codes
date: 2024-11-23 10H:16:00 -0300
categories: [Distributed Systems, Networks]
tags: [distributed-systems, networks, network-protocols, http, https]
author: 0
description:
image:
  path: https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Nokia_Networks_Munich_Office%2C_April_2017_-02.jpg/640px-Nokia_Networks_Munich_Office%2C_April_2017_-02.jpg
  alt: Picture
---
# Standard HTTP response codes.(ilustative table)

| **Family**            | **Code** | **Description**                                                   |
| --------------------- | -------- | ----------------------------------------------------------------- |
| **1XX Informational** | 100      | Continue                                                          |
|                       | 101      | Switching Protocols                                               |
|                       | 102      | Processing                                                        |
|                       | 103      | Early Hints                                                       |
| **2XX Successful**    | 200      | OK (Important Status for SEO)                                     |
|                       | 201      | Created                                                           |
|                       | 202      | Accepted                                                          |
|                       | 203      | Non-Authoritative Information                                     |
|                       | 204      | No Content                                                        |
|                       | 205      | Reset Content                                                     |
|                       | 206      | Partial Content                                                   |
|                       | 207      | Multi-Status                                                      |
|                       | 208      | Already Reported                                                  |
| **3XX Redirection**   | 300      | Multiple Choices                                                  |
|                       | 301      | Moved Permanently (Important Status for SEO)                      |
|                       | 302      | Found (Previously "Moved Temporarily") (Important Status for SEO) |
|                       | 303      | See Other                                                         |
|                       | 304      | Not Modified                                                      |
|                       | 305      | Use Proxy                                                         |
|                       | 306      | Switch Proxy                                                      |
|                       | 307      | Temporary Redirect (Important Status for SEO)                     |
|                       | 308      | Permanent Redirect (Important Status for SEO)                     |
| **4XX Client Error**  | 400      | Bad Request                                                       |
|                       | 401      | Unauthorized                                                      |
|                       | 402      | Payment Required                                                  |
|                       | 403      | Forbidden                                                         |
|                       | 404      | Not Found (Important Status for SEO)                              |
|                       | 405      | Method Not Allowed                                                |
|                       | 406      | Not Acceptable                                                    |
|                       | 407      | Proxy Authentication Required                                     |
|                       | 408      | Request Timeout                                                   |
|                       | 409      | Conflict                                                          |
|                       | 410      | Gone (Important Status for SEO)                                   |
|                       | 411      | Length Required                                                   |
|                       | 412      | Precondition Failed                                               |
|                       | 413      | Payload Too Large                                                 |
|                       | 414      | URI Too Long                                                      |
|                       | 415      | Unsupported Media Type                                            |
|                       | 416      | Range Not Satisfiable                                             |
|                       | 417      | Expectation Failed                                                |
|                       | 418      | I'm a teapot (Joke)                                               |
|                       | 421      | Misdirect Request                                                 |
|                       | 422      | Unprocessable Entity                                              |
|                       | 423      | Locked                                                            |
|                       | 424      | Failed Dependency                                                 |
|                       | 425      | Too Early                                                         |
|                       | 426      | Upgrade Required                                                  |
|                       | 428      | Precondition Required                                             |
|                       | 429      | Too Many Requests                                                 |
|                       | 431      | Request Header Fields Too Large                                   |
|                       | 451      | Unavailable For Legal Reasons                                     |
| **5XX Server Error**  | 500      | Internal Server Error (Important Status for SEO)                  |
|                       | 501      | Not Implemented                                                   |
|                       | 502      | Bad Gateway                                                       |
|                       | 503      | Service Unavailable (Important Status for SEO)                    |
|                       | 504      | Gateway Timeout                                                   |
|                       | 505      | HTTP Version Not Supported                                        |
|                       | 506      | Variant Also Negotiates                                           |
|                       | 507      | Insufficient Storage                                              |
|                       | 508      | Loop Detected                                                     |
|                       | 510      | Not Extended                                                      |
|                       | 511      | Network Authentication Required                                   |
