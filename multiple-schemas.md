---
---

# Using Multiple Schemas

In MySQL and PostgreSQL is is possible to define your entities in multiple schemas. In MySQL 
terminology, it is called database, but from implementation point of view, it is a schema. 

> To use multiple schemas, your connection needs to have access to all of them (multiple 
> connections are not supported).

All you need to do is simply define the table name including schema name in `collection` option:

```typescript
@Entity({ collection: 'first_schema.foo' })
export class Foo { ... }

@Entity({ collection: 'second_schema.bar' })
export class Bar { ... }
```

Then use those entities as usual. Resulting SQL queries will use this `collection` value as a 
table name so as long as your connection has access to given schema, everything should work 
as expected.

[&larr; Back to table of contents](index.md#table-of-contents)
