# HTTP keep-alive机制

## 解决的问题

早期在 http 连接时候，每次连接都会创建一个新的 http 协议，这就导致了一个问题，每次需要经历 http 连接的过程，这就导致了 http 连接非常低效。后来在 http1.1 版本，将 `Connection` 请求头默认改为 `Keep-Alive`值，表示当前连接是持久化的，不会关闭，可以让同一个地址请求，在该连接上继续完成， 直到超出了 `Keep-Alive` 设置的最大超时时间(通过timeout或者max设置)
