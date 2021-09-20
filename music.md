**THE DATASET**

The data being analysed is from the Million Song Dataset
(<http://millionsongdataset.com/pages/getting-dataset/> ) , which is a
freely available collection of audio features and metadata for a million
contemporary popular music tracks.

One of its purposes is to provide a reference dataset for evaluating
research.

The dataset that this project uses is a sample of the main dataset and
contains 10 000 rows of song data, i.e., 1%.

**PURPOSE OF THE PROJECT**

The purpose of this project is to explore the following:

-   Which words in the dataset that describe music genres occur most
    often?

-   Comparisons of song duration, song tempo, and song loudness across
    the four most commonly occurring genres.

-   What correlation exists between song loudness vs song tempo for the
    four most commonly occurring genres.

-   Comparison of song duration, song tempo, and song loudness across
    selected subgenres.

**HOW DATA ARE ANALYSED**

Definition of terms:

-   artist.name (name of artist);

-   artist.terms (genres/subgenres of music);

-   song.duration (total length of a song, measured in seconds);

-   song.loudness (overall volume of a song, measure in decibels. Uses
    negative integers, the smaller the number, the softer the volume,
    i.e. -6dB is louder than -9dB); and

-   song.tempo (measure in beats per minute, or bpm).

The following techniques and methods are used:

-   WordClouds to find the most popular genres of music, both overall
    and the top 50 most commonly occurring genre labels.

-   A bar graph showing the medians of the 4 most popular genres (Rock,
    Pop, Jazz, Blues).

-   Scatterplots ascertaining correlation between song loudness (volume)
    and song tempo for the top 4 genres.

-   Category plots of selected subgenres comparing song duration, song
    tempo, and song loudness.

**MAIN FINDINGS**

The main findings are:

-   The most commonly occurring music genres in the dataset are Rock
    (16.59%), Pop (10.71%), Jazz (5.90%), and Blues (8.26%).

-   Across these 4 genres:

    -   Song duration: The jazz median song duration is quite a bit
        larger than the other genres (247 seconds/4:07), followed by
        Rock (228 seconds/3:48), Pop (220 seconds/3:40), and Blues (208
        seconds/3:28).

    -   Song tempo: Rock has the fastest tempo (123 bpm), followed by
        Pop (121 bpm), Jazz (118 bpm), and Blues (114).

    -   Song loudness: Pop is the loudest genres with a median of
        -8.7dB, followed by Rock (-9.1dB), Blues (-11.4dB), and Jazz
        (-12.9) being the softest.

    -   All four genres show weak correlation between song loudness and
        song tempo.

-   Across selected subgenres:

    -   Hip Hop, Gangster Rap, and Pop Rap are similar to each other in
        song duration, song tempo, and song loudness.
