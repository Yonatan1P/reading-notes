# DRF Premissions

Authentication or identification by itself is not usually sufficient to gain access to information or code. For that, the entity requesting access must have authorization.

permissions determine whether a request should be granted or denied access.

IsAuthenticated class in REST framework: simplest style of permission would be to allow access to any authenticated user

IsAuthenticatedOrReadOnl: allow full access to authenticated users, but allow read-only access to unauthenticated users

HTTP error: "403 Forbidden" or a "401 Unauthorized"

Exceptions raised: PermissionDenied or NotAuthenticated

always defined as a list of permission classes

filter the queryset to find the classes you want to allow premissions on

permission check fails:

- [ ] exceptions.PermissionDenied

- [ ] exceptions.NotAuthenticated

To set up premissions with Django, use the DEFAULT_PERMISSION_CLASSES setting

this setting defaults to allowing unrestricted access

IsAdminUser permission class will deny permission to any user, unless user.is_staff is True

AllowAny permission class will allow unrestricted access, regardless of if the request was authenticated or unauthenticated

HTTP RESTful API methods:

POST requests require the user to have the add permission on the model.

PUT and PATCH requests require the user to have the change permission on the model.

DELETE requests require the user to have the delete permission on the model.

## Questions
Where are the admin users actually defined? 

Can there be restful calls to change the admin status of the user?

