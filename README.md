
# o-auth
Polymer custom element for single site oauth.

## Inspired by
http://blog.vjeux.com/2012/javascript/github-oauth-login-browser-side.html

### Basic workflow

![oauth workflow](http://blog.vjeux.com/wp-content/uploads/2012/03/githublogin1.png)

## Getting started



## Usage

`<oauth></oauth>` has following...

##### Attributes

- `service` __(required)__

> Is the URL to the oauth service. (like for github: https://github.com/login/oauth/authorize)

- `client` __(required)__

> The _client id_ or also sometimes called _app key_.

- `params` _default: ''_

> Extra parameters to pass on to the service URL.
> Can be an object or just a query string. (e.q. 'scope=user:email')

- `listen` _default: 'oauth=o-auth'

> This is the key that this element needs to recognize if returned URI is from
> the given service.
>
> __Note:__ if you have serveral `<o-auth>` tags on your page (e.g. for different
> services) you should change this in order that every element gets its right call/
> code. (if you use it for github change it for example to _oauth=github_)

- `width` _default: 600_

> The width of the popup.

- `height` _default: 800_

> The height of the popup.

- `popup`

> Reference to the popup itself.

- `code`

> Is the returned code needed for further authentication. Also it will be stored
> in the local storage of the user if `save` is `yes`

- `save` _default: yes_

> Whether to store code token returned from given service.

##### Methods:

- `oauth()`

> Starts the whole process with opening the popup to the specified service.

##### Events

- `success`

> If everything worked out and a code was received.

- `error`

> An error occurred. In this case likely a 3rd party attack. CSRF code was a miss match.

- `opened`

> Popup was opened.

- `closed`

> Popup was closed.


###### One example at last

```html
<!-- Github oauth service. Popup fits perfectly. -->
<o-auth
  id="oauth"
  service="https://github.com/login/oauth/authorize"
  client="[client-id]"
  params="scope=user:email"
  code="{{code_binding}}"
  listen="oauth=github"
  width="1030"
  height="618"></o-auth>
```


## Next steps
Do whatever your specified service says to do. Use the `code` wise.

## Current status
Works for me right now. Changes to fit more services in future maybe.

If more examples are needed have a look into predefined elements for several services:

- Github: https://github.com/mui-is/oauth-github
- Dropbox: https://github.com/mui-is/oauth-dropbox
- Goggle Drive: https://github.com/mui-is/oauth-googledrive

## Donations
Please help me to finance my every cup of tea. Every coin is appreciated.

```
Sick of tea? That’s like being sick of *breathing*! - Uncle Iroh
```

`197EypPopXtDPFK6rEbCw6XDEaxjTKP58S`[ -- bitcoin](http://en.wikipedia.org/wiki/Bitcoin)

`jan.guth@gmail.com`[ -- paypal](https://www.paypal.com/us/webapps/mpp/home)

[Or just `flattr`  me.](https://flattr.com/submit/auto?user_id=jguth&url=https://github.com/fentas)
