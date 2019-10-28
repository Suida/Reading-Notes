# Request

- Extends `HttpRequest`
- Incoming data
  - `.data`: parsed content of the request body (`POST`, `PUT`, `PATCH`)
  - `.query_params`: synonym for `request.GET`
  - `.parsers`: a list of `Parser` instance to parse request content
- Content negotiation
  - `.accepted_renderer`: `Renderer` instance
  - `.accepted_media_type`: `str`
- Authentication
  - `.user`: `django.contrib.auth.models.User` or `django.contrib.auth.models.AnonymousUser`
  - `auth`: additional authentication context depending of authentication policy used
  - `.authenticators`: set by `@api_view` or based on `authentication_classes` of `APIVIEW` or `DEFAULT_AUTHENTICATORS` setting
- Browser enhancements
  - `method`: **uppercased** method string
  - `.content_type`: string representin the media type
  - `.stream`: a stream representing the content of the request body
- Any other attributes present in Django's `HttpRequest`
