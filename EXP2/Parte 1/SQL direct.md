## Descripción del reto
¡Conéctese a este servidor PostgreSQL y encuentre la bandera!
Detalles adicionales estarán disponibles después de lanzar su instancia de desafío.
## Pistas 
¿Qué contiene una base de datos SQL?
## Solución 
resm-picoctf@webshell:~$ 
resm-picoctf@webshell:~$ psql -h saturn.picoctf.net -p 50029 -U postgres pico
Password for user postgres: 
psql (14.11 (Ubuntu 14.11-0ubuntu0.22.04.1), server 15.2 (Debian 15.2-1.pgdg110+1))
WARNING: psql major version 14, server major version 15.
         Some psql features might not work.
Type "help" for help.

pico=# show databases
pico-# ls -la
pico-# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)
pico=# select * from public.flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)
## Contraseña obtenida 
picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}
## Notas 
Aprendí a visulizar que contiene las tablas de una manera mas objetiva y poder analizar un poco más lo que vienen siendo las bases de datos. 
## Referencias 
https://cloud.google.com/spanner/docs/psql-commands?hl=es-419
