# MegaBytes Organization

## Front-End Deployment 
For when stories are completed and deployment to aws is ready to go.

### React
Make sure you have a ```.env``` file setup with ```REACT_APP_BACKEND_ADDRESS=CLOUDFRONT_ADDRESS```.
The CLOUDFRONT_ADDRESS should be the cloudfront domain pointing to the load balancer.

Then run ```npm run build```. Once the build is successful a ```dist``` folder will be created along with all the files needed to deploy to S3.
Once a bucket has been created for the specific portal. You can upload all the files inside ```dist``` to the bucket

### Angular

#### Customer Front-End

To configure the project for deployment, find `src/environments/environment.prod.ts` and add/replace the `basePath` key in the JSON to the address of the backend.

__environment.prod.ts__
```
export const environment = {
  production: true,
  basePath: BACKEND_ADDRESS
};
```
Once configured `ng build` will build the artifacts to `dist/` which contain the files to be deployed to a server.

#### Restaurant Manager Front-End

To configure the project for deployment, find `src/environments/environment.prod.ts` and add/replace the `BACKEND_ADDRESS` key in the JSON to the address of the backend.

__environment.prod.ts__
```
export const environment = {
  production: true,
  BACKEND_ADDRESS: PATH
};
```
Once configured `ng build` will build the artifacts to `dist/` which contain the files to be deployed to a server.
