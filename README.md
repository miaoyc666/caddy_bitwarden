# caddy_bitwarden
使用docker-compose管理的bitwarden个人密码库服务

#### 使用步骤
1. 申请https证书（申请过程请各显神通）
2. 创建caddy_data和bw_data目录到数据目录，例如mkdir -p /share/caddy_data/, mkdir -p /share/bw_data/
3. 将https证书放入caddy_data目录，例如放入myc.ink.key和myc.ink.pem
4. 将Caddyfile、localtime和timezone拷贝到caddy_data目录
5. 使用docker-compose启动服务，docker-compose -f caddy_bitwarden.yaml up -d
6. 登录myc.ink:5102（此处地址为示例），注册用户
7. 注册用户后，修改caddy_bitwarden.yaml中的SIGNUPS_ALLOWED参数为false，关闭用户注册
8. 在bitwarden内部打开二次认证，即完成个人密码库的部署