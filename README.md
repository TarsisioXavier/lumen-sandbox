# Lumen Sandbox

This is just a sandbox for study, nothing special.
Here you'll find:
- Lumen;
- Docker compose;
- Docker Images;
- And container working together;

## 🌳 The Environment
I've created a sub network for all these containers so they can "talk" to each other.  
Here's the IP mapping I've made:

### 172.40.10.1x - Databases and Services
Here I like to serve thing like databases, mail services and etc. Here's the services listed.
- MySQL under IP 172.40.10.10;
- Redis under IP 172.40.10.11;
- Mailhog under IP 172.40.10.12;

### 172.40.10.2x - PHP Servers
For now, there is only one server running PHP-FPM 8.1 under the IP 172.40.10.20.

### 172.40.10.3x - NginX Servers
This range its dedicated for the servers, so the IP 172.40.10.30 contains the nginx serving the lumen files.

## 🚀 Running
Just open http://172.40.10.30/ on your browser after running:
```bash
docker-compose up -d
```

Whenever you want to use php tools like `composer` or `artisan`, you need to get inside the PHP container using:
```bash
docker exec -ti --user=lumen php-fpm81 sh
```

## 🧪 Testing
Get inside the PHP container using:
```bash
docker exec -ti --user=lumen php-fpm81 sh
```

Once inside, just run:
```bash
composer test
```
