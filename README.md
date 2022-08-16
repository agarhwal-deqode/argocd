1. deploying 2 applications mongodb and mongoexpress
2. mongo-express (web application) -> requesting to the database -> mongo-db
3. first we will create a mongo db pod - in order to talk to that pod we need a mongo db service. We are going to create an interna; service that means no external request can get through the pod, only the components of the cluster are able to get through the pod.
4. then we will create an mongo-express deplolyment [need a DB url of mongodb so that mongo express can connect to it] user name and password so that we can auathenticate. we can apss to mongo-express deployment is through environment variables, whose value will be gven by config maps and secrets. referencing both in the mongo-express deployment file
5. Now we want to access mongo exprress from an browser so we need to create an external service to talk to the pod.
6. request flow [browser -> mongoexpress external service -> mongo express pod -> internal service of mongo db that is db url -> mongodb pod -> authen ticate using the mongo db creds which is in the secrets]
7. creating the mong.yml as deployment and secrets for db