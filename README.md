# Intro to SQL

1. Install the SQLite Browser if you haven't already [here](http://sqlitebrowser.org/)
2. Open the SQLite Browser and click 'File -> Open DataBase'
3. Choose the `chinook.db` file from this repo. This database is open source and maintained by Microsoft (SQL is no fun if you don't have any data)
4. Click the tab that says 'Execute SQL'. Type SQL queries in the box above. Press the play button. See the results of that query in the box below



## Challenges

1. Write the SQL to return all of the rows in the artists table?

```SELECT * 
FROM artists;

```

2. Write the SQL to select the artist with the name "Black Sabbath"

```SELECT * FROM artists 
WHERE artists.Name = 'Black Sabbath';

```

3. Write the SQL to create a table named 'fans' with an autoincrementing ID that's a primary key and a name field of type text

```CREATE TABLE fans (
	id INTEGER PRIMARY KEY,
	name TEXT
);

```

4. Write the SQL to alter the fans table to have a artist_id column type integer?

```ALTER TABLE fans ADD COLUMN artist_id INTEGER;

```

5. Write the SQL to add yourself as a fan of the Black Eyed Peas? ArtistId **169**

```INSERT INTO fans (name, artist_id) VALUES ('EJ', 169);

```

6. Check out the [Faker gem](https://github.com/stympy/faker). `gem install faker`, open up irb, run `require 'faker'` and then generate a fake name for yourself using `Faker::Name.name`. How would you update your name in the fans table to be your new name?

   ```UPDATE fans 
   SET name = 'Lawanna Langosh' 
   WHERE name = 'EJ';

   ```

7. Write the SQL to return fans that are not fans of the black eyed peas.

```SELECT fans.name 
FROM fans 
JOIN artists 
ON fans.artist_id = artists.ArtistId 
WHERE artists.name != 'Black Eyed Peas';

```

8. Write the SQL to display an artists name next to their album title

```SELECT artists.name, albums.Title 
AS album_title 
FROM artists 
JOIN albums 
ON artists.ArtistId = albums.ArtistId 
ORDER BY artists.name;

```
