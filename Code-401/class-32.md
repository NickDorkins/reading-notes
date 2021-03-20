# Class 32: Permissions & Postgesql

## [DRF Permissions](https://www.django-rest-framework.org/api-guide/permissions/)


# Permissions

Permission checks are always run at the very start of the view, before any other code is allowed to proceed. Permission checks will typically use the authentication information in the `request.user` and `request.auth` properties to determine if the incoming request should be permitted.

The simplest style of permission would be to allow access to any authenticated user, and deny access to any unauthenticated user. This corresponds to the `IsAuthenticated` class in REST framework.

A slightly less strict style of permission would be to allow full access to authenticated users, but allow read-only access to unauthenticated users. This corresponds to the `IsAuthenticatedOrReadOnly` class in REST framework.

## How permissions are determined

Permissions in REST framework are always defined as a list of permission classes.

Before running the main body of the view each permission in the list is checked. If any permission check fails an `exceptions.PermissionDenied` or `exceptions.NotAuthenticated` exception will be raised, and the main body of the view will not run.

When the permissions checks fail either a "*403 Forbidden*" or a "*401 Unauthorized*" response will be returned, according to the following rules:

The request was successfully authenticated, but permission was denied. — An HTTP 403 Forbidden response will be returned.
The request was not successfully authenticated, and the highest priority authentication class does not use `WWW-Authenticate` headers. — An HTTP 403 Forbidden response will be returned.
The request was not successfully authenticated, and the highest priority authentication class does use `WWW-Authenticate` headers. — An HTTP 401 Unauthorized response, with an appropriate `WWW-Authenticate` header will be returned.

## [Classy Django REST](http://www.cdrf.co/)

## [DRF Generic Views](https://www.django-rest-framework.org/api-guide/generic-views/)