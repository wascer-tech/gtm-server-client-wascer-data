# Data Client Wascer

A Google Tag Manager **server** client that turns incoming HTTP requests into
events your tags can consume. It claims the paths you configure, maps request
data into event data, and gives you control over cookies and the response the
browser gets back.

Built by [Wascer](https://wascer.com) for the server containers we host, and free
for anyone to use.

## What the template does

1. Claims the request paths you list and maps request data into event data.
2. Optionally exposes the FPID cookie, and can set it as HTTP only.
3. Can generate a client id and prolong existing cookies on every request.
4. Accepts multiple events in a single request.
5. Lets you shape the response: status code, regular body, redirect, or client error.

## Installation

1. In your **server** container, open **Templates**, then **Client Templates**,
   then **New**.
2. Open the three dot menu and choose **Import**.
3. Pick `template.tpl` from this repository and save.
4. Create a client from the template and set the paths it should claim.

## Fields

| Field | Type | What it does |
|---|---|---|
| Expose FPID cookie | Checkbox | Writes the FPID cookie so later requests carry the same identifier. |
| HTTP only cookie | Checkbox | Marks the cookie HTTP only, hiding it from client side scripts. |
| Generate client id | Checkbox | Creates a client id when the request does not carry one. |
| Prolong cookies | Checkbox | Refreshes cookie expiry on every claimed request. |
| Accept multiple events | Checkbox | Reads more than one event from a single request body. |
| Response Settings | Group | Status code plus the regular, redirect and client error response bodies. |
| Accepted Path Settings | Table | Extra paths claimed by this client, on top of the default. |

## Requirements

A Google Tag Manager **server** container.
Templates published by Wascer are tested against the container images we host.

## Support

Open an issue in this repository, or reach the team at
[wascer.com](https://wascer.com). If you host your server container with Wascer,
support is included in your plan.

## License

Apache License 2.0. See [LICENSE](LICENSE).
