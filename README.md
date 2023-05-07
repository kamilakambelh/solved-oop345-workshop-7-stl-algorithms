Download Link: https://assignmentchef.com/product/solved-oop345-workshop-7-stl-algorithms
<br>
In this workshop, you use the Algorithm category of the Standard Template Library.

You are going to create an application that manages a collection of songs.

## *In-Lab*

The in-lab portion of this workshop consists of modules:– `w7` (supplied)– `SongCollection`

Enclose all your source code within the `sdds` namespace and include the necessary guards in each header file.

In the specs below, functions marked with `DO NOT USE MANUAL LOOPS` should not use `for` or `while` in the implementation; these functions should use STL Algorithms. Check course notes to identify which algorithm is appropriate in each situation.  Using manual loops will lead to **rejection** of the workshop or **severe penalties** (at the discretion of your professor).

### `SongCollection` Module

This modules defines a simple structure called `Song`, capable of storing the following information about a single song:– artist– title– album– price– release year– length of the song

No need to add any member functions to this structure. Choose appropriate types for each attribute.

Also, define a class called `SongCollection` that manages a collection of objects of type `Song`.

***Public Members for `SongCollection`***

– a custom constructor that receives as a parameter the name of the file containing the information about the songs to be added to the collection. This function should load into the attributes all the songs in the file.

If the filename is incorrect, this constructor should throw an exception.

Each line from the file contains information about a single song in the following format:“`TITLE ARTIST ALBUM YEAR LENGTH PRICE“`The fields are not separated by delimiters; each field has a fixed size: `TITLE`, `ARTIST` and `ALBUM` have **exactly** 25 characters; while `YEAR`, `LENGTH` and `PRICE` have **exactly** 5 characters.

The length of a song in the input file is stored in seconds.

Any blank space at the begining/end of a token is not part of the token and should be removed.

– `void SongCollection::display(std::ostream&amp; out) const`: print the content of the collection into the parameter (one song / line). Use the insertion operator (see below). ***DO NOT USE MANUAL LOOPS!***

***Free Helpers***

– `std::ostream&amp; operator&lt;&lt;(std::ostream&amp; out, const Song&amp; theSong)`: inserts one song into the first parameter, using the following format (the width of each field is specified in brackets):“`| TITLE(20) | ARTIST(15) | ALBUM(20) | YEAR(6) | LENGTH | PRICE |“`

Look in the sample output to see how the numbers should be formatted and the alignment of each field.

**Add any other member that is required by your design!**

### `w7` Module (supplied)

The tester module for the in-lab portion has been supplied. **Do not modify the existing code!**

When doing the workshop, you are encouraged to write your own tests, focusing on a single implemented feature at the time, until you get all functionality in place.

### Sample Output

When the program is started with the command (the file `songs.txt` is provided):“`w7.exe songs.txt“`the output should look like the one from the `sample_output.txt` file.

“`Command Line:————————–1: w7.exe2: songs.txt————————–

—————————————————————————————-| The original collection                                                              |—————————————————————————————-| Bird Set Free        | Sia             | This Is Acting       |   2016 | 4:12 | 1.21 || Fight Song           | Rachel Platten  | [None]               |   2015 | 3:24 | 1.25 || ..Baby One More Time | Britney Spears  | [None]               |   1999 | 3:30 | 1.29 || One Million Bullets  | Sia             | This Is Acting       |   2016 | 4:12 | 1.23 || (You Drive Me) Crazy | Britney Spears  | Baby One More Time   |   1999 | 3:18 | 1.29 || Cheap Thrills        | Sia             | This Is Acting       |   2016 | 3:31 | 1.29 || Dream On             | Amy Macdonald   | Under Stars          |   2017 | 3:19 | 1.29 || Dream Is Collapsing  | Hans Zimmer     | Best of              |   2014 | 2:23 | 1.29 || Hot N Cold           | Katy Perry      | [None]               |   2008 | 3:40 | 1.14 || Circus               | Britney Spears  | Circus               |   2008 | 3:12 | 1.29 || Under Stars          | Amy Macdonald   | Under Stars          |   2017 | 3:41 | 1.29 || Rafiki’s Fireflies   | Hans Zimmer     | Best of              |   2017 | 1:52 | 1.29 || Song Of Ocarina      | Diego Modena    | [None]               |   1991 | 3:35 | 0.49 || Sometimes            | Britney Spears  | Baby One More Time   |   1999 | 4:05 | 1.29 || Alive                | Sia             | This Is Acting       |   2016 | 4:23 | 1.22 || Why so Serious?      | Hans Zimmer     | Best of              |   2016 | 9:14 | 1.29 || Ain’t It Funny       | Jennifer Lopez  | [None]               |        | 4:17 | 0.99 || Chandelier           | Sia             | [None]               |   2014 | 3:36 | 1.32 || Break the Ice        | Britney Spears  | Blackout             |   2007 | 3:16 | 1.29 || Moonlight Reggae     | Diego Modena    | [None]               |   2010 | 4:43 | 1.19 |—————————————————————————————-“`

## *At-Home*

The *at-home* part of this workshop upgrades your *in-lab* solution to include more functionality in the `SongCollection` module.

### `SongCollection` Module

***Public Members***

– `void SongCollection::display(std::ostream&amp; out) const`: update this function to display the playtime of the entire collection (the total playtime is the sum of the length attribute of all songs). See the sample output for the format.  ***DO NOT USE MANUAL LOOPS!***

– `void sort()`: receives as a parameter the name of the field used to sort the collection of songs in ascending order. The parameter can have one of the values `title`, `album`, or `length`.  ***DO NOT USE MANUAL LOOPS!***

– `void cleanAlbum()`: removes the token `[None]` from the album field of the songs that do not have a valid album.  ***DO NOT USE MANUAL LOOPS!***

– `bool inCollection() const`: receives the name of an artist as a parameter, and returns `true` if the collection contains any song by that artist.  ***DO NOT USE MANUAL LOOPS!***

– `std::list&lt;Song&gt; getSongsForArtist() const`: receives the name of an artist as a parameter, and returns the the list of songs of that artist available in the collection.  ***DO NOT USE MANUAL LOOPS!***

### `w7` Module

The tester module for the at-home portion has been supplied. **Do not modify the existing code!**

When doing the workshop, you are encouraged to write your own tests, focusing on a single implemented feature at the time, until you get all functionality in place.

### Sample Output

When the program is started with the command (the input file is provided):“`w7.exe songs.txt“`the output should look like the one from the `sample_output.txt` file.