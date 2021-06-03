## K8S deployments for the common open source products


### Apache2 httpd 2.4 as forward proxy

- Refer to the files under [./apache2-fwd-proxy](https://github.com/nilaybose/k8sdeployments/tree/main/apache2-fwd-proxy)
- Following .so are enabled in the httpd.conf present in the ConfigMap

```shell
    LoadModule proxy_module modules/mod_proxy.so
    LoadModule proxy_connect_module modules/mod_proxy_connect.so
    LoadModule proxy_http_module modules/mod_proxy_http.so
    LoadModule ssl_module modules/mod_ssl.so   
```

- Enable the proxy section in httpd.conf

```shell
  ProxyRequests On
  ProxyVia On
  <Proxy "*">
  </Proxy>
```

*NOTE* - Configure the proxy section with security and hardening