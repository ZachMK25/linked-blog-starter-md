used to modify attribute values

a WHERE-clause selects the tuple(s) to be modified

An additional SET-clause specifies the attributes to be modified

ex: UPDATE Project SET PLocation = 'Bellaire', DNum = 5 WHERE PNumber=10;

ex: UPDATE Employee SET Salary=Salary * 1.1 WHERE Dno IN (SELECT DNumber FROM Department WHERE Dname='Research')
- Nested Queries