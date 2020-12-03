# node_oauth


docker run --name postgres_oauth -e POSTGRES_PASSWORD=pass1234 -e POSTGRES_USER=userexample -d postgres

psql ->

CREATE TABLE public.users
(
    id serial,
    username text,
    user_password text,
    PRIMARY KEY (id)
)
WITH (
    OIDS = FALSE
);

ALTER TABLE public.users
    OWNER to userexample;



CREATE TABLE public.access_tokens
(
    id serial,
    access_token text,
    user_id integer,
    PRIMARY KEY (id)
)
WITH (
    OIDS = FALSE
);

ALTER TABLE public.access_tokens
    OWNER to userexample;


https://blog.logrocket.com/implementing-oauth-2-0-in-node-js/