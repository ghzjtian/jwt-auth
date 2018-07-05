# JWT 的框架

* [1.Github 地址](https://github.com/tymondesigns/jwt-auth)
* [2.认证的 token 的几种方法](http://jwt-auth.readthedocs.io/en/develop/quick-start/#authenticated-requests)
    * 1.如果是在 `header` 中认证，就为 `Authorization: Bearer eyJhbGciOiJIUzI1NiI...`
    * 2.其它，如 `Query string` `Post parameter` `Cookies` 等等，就用  `token` 为 key ,后面接相应的值.
    
* 3.要注意认证的 `middleware` 为 `api` ,而不是 `auth:api`


* 4.账号的密码为 123456.

* 5.发现的问题
    * 1.在 `config/auth.php` 中改变了默认的 `guard` ,如把 `web` 改为 `api`,则 `api` 方面登录拿到 `token` 后，可以正常地用 `token` 拿到数据，但是在浏览器中的登录会被弹出，一直登录不上，反之改变 `default/guard` 为 `web` 也一样.
    * 2.解决方法: 
        * 1.在 `config/auth.php` 中修改 `default->guard` 为 `web`
        * 2.在 `APP\Http\Controller\AuthController` 中加入 
        ``` protected function guard()
               {
                   return Auth::guard('api');
               }
         ```
