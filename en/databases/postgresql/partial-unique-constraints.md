# Partial Unique Constraints

PostgreSQL supports partial unique indices but it's not possible to set up deferrable
on them. The alternative is to create an exclude constraint. Here's an example:

    create table jurisdictions(
      id serial primary key,
      name text not null check (name <> ''),
      parent_id integer references jurisdictions(id),
      position integer not null,
      exclude ((array[position, parent_id]) with =) deferrable initially deferred
    );
