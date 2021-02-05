# A Few Notes Re: `vhost.d` Files

Each file should be coded as an additional nginx "location" block.

```nginx
 location /<PATH_OR_BLANK> {
  proxy_pass_header Set-Cookie;
  proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  proxy_set_header X-Forwarded-Proto $scheme;
  proxy_set_header X-Real-IP $remote_addr;
  proxy_set_header Host $http_host;
  proxy_pass http://<SERVER_IP_OR_DOMAIN>:5050/<PATH_OR_BLANK>;
 }
```
