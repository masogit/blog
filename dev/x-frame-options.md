## X-FRAME-OPTIONS
很多网页不允许iframe显示

```
X-Frame-Options 有三个值:

DENY

表示该页面不允许在 frame 中展示，即便是在相同域名的页面中嵌套也不允许。

SAMEORIGIN

表示该页面可以在相同域名页面的 frame 中展示。

ALLOW-FROM uri

表示该页面可以在指定来源的 frame 中展示。

换一句话说，如果设置为 DENY，不光在别人的网站 frame 嵌入时会无法加载，在同域名页面中同样会无法加载。

另一方面，如果设置为 SAMEORIGIN，那么页面就可以在同域名页面的 frame 中嵌套。
```

tomcat配置如下
```
<filter>
  <filter-name>httpHeaderSecurity</filter-name>
  <filter-class>org.apache.catalina.filters.HttpHeaderSecurityFilter</filter-class>
  <init-param>
    <param-name>antiClickJackingEnabled</param-name>
    <param-value>true</param-value>
  </init-param>
  <init-param>
    <param-name>antiClickJackingOption</param-name>
    <param-value>SAMEORIGIN</param-value>
  </init-param>
  <async-supported>true</async-supported>
</filter>
<filter-mapping>
  <filter-name>httpHeaderSecurity</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>
```

nginx配置, nginx.conf
- add_header X-FRAME-OPTIONS SAMEORIGN;

