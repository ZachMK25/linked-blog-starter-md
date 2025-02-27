Removed tuples from a relation

includes a where clause to select the tuples to be deleted

referential integrity should be enforced

tuples are deleted from only *one table* at a time (unless CASCADE is specified on a referential integrity constraint)

a missing WHERE-clause specifies that *all tuples* in the relation are to be deleted

ex: DELETE FROM Employee WHERE Lname='Brown';

DELETE FROM Employee;
- Deletes all tuples in the relation/table