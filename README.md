1. Create an account on Heroku
1. Create an app named `kennel-server`
1. Install Heroku CLI
1. Login to Heroku
1. Add `Procfile` to project
    ```
    web: python request_handler.py $PORT
    ```
1. Change end of request handler to the following code
    ```py
    def main():
        host = ''
        port = int(os.environ['PORT'])
        HTTPServer((host, port), HandleRequests).serve_forever()


    main()
    ```
1. `heroku git:remote -a kennel-server`
1. Activate dyno with `heroku ps:scale web=1`