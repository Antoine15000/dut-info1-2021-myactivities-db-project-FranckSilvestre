CREATE OR REPLACE find_activities_older_than(
    old_date DATE )
RETURNS SETOF activity AS $$ 
SELECT *
FROM activity 
WHERE modification_date <= old_date 
$$ LANGUAGE SQL; 
SELECT * FROM find_activities_older_than('2019-9-10')
