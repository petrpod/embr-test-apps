# Flask test app

`builder.yaml` configures this repository as one App Service Builder Python web
component. It preserves the Python 3.14 version request from the legacy
`build.yaml`; the selected deployment target must provide that version.

Dependencies come from `requirements.txt`. Gunicorn serves `app:app` on
`0.0.0.0:8080`, and the existing `/` page is the deployment health check, which
must return HTTP 200. Flask continues to serve the templates and static files.

The legacy `build.yaml` is retained for reference. Current Builder deployments
use `builder.yaml`. Commit and push the manifest before deploying because
Builder builds committed GitHub source, not local working-directory changes.