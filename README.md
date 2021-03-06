# Guestbook Demo

## Components

### Frontend

Source code: https://github.com/kadel/guestbook-demo-frontend

Nginx server that servers html and javascript files.

Nginx also acts as reverse proxy for backend api server.


```
        location /api/comments {
            proxy_pass http://backend:3000/api/comments;
        }
```

### Backend

Source code: https://github.com/kadel/guestbook-demo-backend

Simple api server to save and read comments that saves comments to MongoDB database.


### Database

MongoDB database to save comments.

Typicaly [bitnami/mongodb](https://hub.docker.com/r/bitnami/mongodb/tags/) image is used.



## KedgeFiles

Files to that can be used to deploy application using [Kedge](https://github.com/kedgeproject/kedge)

### [KedgeFiles/simple/kedge.yml](https://github.com/kadel/guestbook-demo/tree/master/KedgeFiles/simple)

The most simple Kedge file for this application 

### [KegeFiles/onfigMapsAndSecrets/](https://github.com/kadel/guestbook-demo/tree/master/KedgeFiles/configMapsAndSecrets)

More complicated example that uses Kubernetes Secrets and Config Maps.