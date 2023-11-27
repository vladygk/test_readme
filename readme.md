# Blog app

![Alt text](./readmePhotos/arch.png)

## Structure:
    - ** Backend API **:
        **NodeJS/ExpressJS** HTTP Server with a GRPC client
        MongoDB to keep the Posts and Comments entities
    - **Backend Authentication service**
        **Golang** GRPC Server handling the user authentication
        MongoDB to keep the User entity
    - **Frontend React service**
        Written in **React** and **TypeScript**
        Monochrome design

## How to run:
    From root folder:
    **Backend API**: ` cd ./blog-app-api; npm start `
    **Backend Authentication service**: `cd ./blog-app-auth-service; go run main.go`
    **Frontend React service**: `cd ./blog-app-frontend; npm run dev`
## Flow:
    The user interacts with the frontend
        making HTTP request to the **Backend API**
    If a request is related to the **User** entity, the **Backend API** 
        makes a **GRPC** call to the **Backend Authentication service**
    If not the **Backend API** responds to the **Frontend React service**
    The **Backend Authentication service** responds with a **JWT**
        token or with a User **protobuffer** message, which is forwarded by
        the **Backend API** to the **Frontend React service**
## Key features:
    - JWT authentication
    - Independent scalability for the Backend API and the Backend Authentication service
    - Responsive design

## Photos:

![Alt text](./readmePhotos/home.png)
![Alt text](./readmePhotos/login.png)
![Alt text](./readmePhotos/posts1.png)
![Alt text](./readmePhotos/postCreate1.png)
![Alt text](./readmePhotos/posts2.png)
![Alt text](./readmePhotos/comments.png)