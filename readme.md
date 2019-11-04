# Example of non-sequential Laravel keys

Using non-sequential keys helps to avoid disclosing information.

If your primary key is an auto-incrementing id then your urls will be predictable, making it easier for a hacker to exhaustively test your authorization.

## How it works

A trait `\App\Traits\UsesUuid` is added to the model where we want to use a uuid as the PK.

## Running the project

You can use the included docker-compose stack to run the project.

    cd docker
    docker-compose up -d
    docker exec -it php /bin/bash
    composer install
    php artisan migrate
    php artisan db:seed
    
## Seeing it in action

Visit `http://localhost:8000/users` in your browser to see a list of users.
Notice that they have a UUID as their id.

A user will not be able to guess the url that another users information will be available on.