# P1 - PL-SQL code

**Problem Statement:** Write a PL/SQL code block to calculate the area of a circle for a value of radius varying from 5 to 9. Store the radius and the corresponding values of calculated area in an empty table named areas, consisting of two columns, radius and area.

---

## Procedure
```plsql
DECLARE
  radius NUMBER;
  area NUMBER;
  nodata EXCEPTION;
BEGIN
  DBMS_OUTPUT.PUT_LINE('Enter radius: ');
  radius := &radius; -- for Live SQL, specify a value. Eg. radius := 5;

  IF NOT (radius BETWEEN 5 AND 9) THEN
    raise nodata;
  END IF;

  area := 3.14 * radius * radius;

  DBMS_OUTPUT.PUT_LINE('Area of circle with radius ' || radius || ' cm is ' || area || ' sq.cm.');
EXCEPTION
  WHEN nodata THEN
    DBMS_OUTPUT.PUT_LINE('Radius should be between 5 and 9.');
END;
/

```

---