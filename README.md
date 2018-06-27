# JWT 的框架

* [1.Github 地址](https://github.com/tymondesigns/jwt-auth)
* [2.认证的 token 的几种方法](http://jwt-auth.readthedocs.io/en/develop/quick-start/#authenticated-requests)
    * 1.如果是在 `header` 中认证，就为 `Authorization: Bearer eyJhbGciOiJIUzI1NiI...`
    * 2.其它，如 `Query string` `Post parameter` `Cookies` 等等，就用  `token` 为 key ,后面接相应的值.
* 3.要注意认证的 `middleware` 为 `api` ,而不是 `auth:api`




