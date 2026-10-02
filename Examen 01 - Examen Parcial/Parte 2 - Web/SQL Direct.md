**SQL Direct**

Descripción

Connect to this PostgreSQL server and find the flag! **psql -h chatelaine.cylabacademy.net -p 43526 -U postgres pico**

Password is **postgres**

Solución:

```

MaxSteel09-academy@webshell:~$ psql -h chatelaine.cylabacademy.net -p 43526 -U postgres pico

Password for user postgres:

psql (14.22 (Ubuntu 14.22-0ubuntu0.22.04.1), server 18.6 (Debian 18.6-1.pgdg13+2))

WARNING: psql major version 14, server major version 18.

         Some psql features might not work.

Type "help" for help.

pico=# \d

         List of relations

 Schema | Name  | Type  |  Owner  

--------+-------+-------+----------

 public | flags | table | postgres

(1 row)

pico=# SELECT * FROM flags;

 id | firstname | lastname  |                address                

----+-----------+-----------+----------------------------------------

  1 | Luke      | Skywalker | academy{L3arN_S0m3_5qL_t0d4Y_d4538dde}

  2 | Leia      | Organa    | Alderaan

  3 | Han       | Solo      | Corellia

(3 rows)

pico=#

```

academy{L3arN_S0m3_5qL_t0d4Y_d4538dde}