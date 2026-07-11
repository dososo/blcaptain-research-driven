# Public Research Example

## Question

Does Python 3.8's default `urllib.request.HTTPRedirectHandler` follow an HTTP 308 redirect, and does Python 3.13 preserve non-GET methods automatically?

## Conclusion

- Python 3.8: the default handler does not natively follow HTTP 308 — **Probable**.
- Python 3.13: the default handler follows HTTP 308 for GET and HEAD, but does not automatically replay POST, PUT, PATCH, or DELETE — **Probable**.

## Why

The versioned CPython implementation, official documentation, redirect tests, and HTTP redirect specifications agree on the observed method boundary. These materials share upstream ancestry, so the grades remain Probable rather than Confirmed under the Skill's independence rule.

## Countercheck

The strongest alternative was: "modern urllib follows 308 for every method while preserving the method and body." Versioned source and controlled behavior did not show redirected POST or PUT requests.

## Boundaries and gaps

- Custom redirect handlers and vendor-patched Python builds are outside scope.
- A direct runtime check for every Python minor version was not assumed.
- The conclusion does not claim that HTTP 308 is universally handled the same way by every HTTP client.

## Source plan

- CPython versioned source and tests.
- Python versioned documentation.
- RFC 7538 and RFC 9110.
