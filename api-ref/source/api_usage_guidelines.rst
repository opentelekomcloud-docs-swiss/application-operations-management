:original_name: aom_04_0000.html

.. _aom_04_0000:

API Usage Guidelines
====================

Cloud APIs comply with the RESTful API design principles. REST-based web services are organized into resources. Each resource is identified by one or more Uniform Resource Identifiers (URIs). An application accesses a resource based on the resource's Unified Resource Locator (URL). A URL is usually in the following format: https://*Endpoint/uri*. In the URL, *uri* indicates the resource path, that is, the API access path.

Cloud APIs use HTTPS as the transmission protocol. Requests/Responses are transmitted using JSON messages, with the media type represented by **Application/json**.

For details about metric description, see **Metric Description**\  in the \ *AOM User Guide*\ .
