# Classification

# Question/need:

### What is the framing question of your analysis, or the purpose of the model/system you plan to build?

How well can I predict the emotion of a song based on musical characteristics as well as the lyrics?

### Who benefits from exploring this question or building this model/system?

A wide variety of parties benefit from exploring music reliably by emotion:  businesses or restaurants looking to impart a specific feeling or mood, music therapists seeking to relate to a client but unfamiliar with the client's preferred genre, and anyone who has had a bad day and wants to hear something relatable. Also, I think it will be a fun and interesting question to explore.

# Data Description:

### What dataset(s) do you plan to use, and how will you obtain the data?

There are several datasets that are available and relevant to music emotion recognition (MER). 

- Music Dataset: A csv containing artist, song, year, lyrics, Spotify features, and more of over 80,000 songs. This dataset was compiled for a paper: Moura, Luan; Fontelles, Emanuel; Sampaio, Vinicius; França, Mardônio (2020), “Music Dataset: Lyrics and Metadata from 1950 to 2019”, Mendeley Data, V3, doi: 10.17632/3t9vbwxgr5.3
- Spotify: I can generate a database of songs and their metadata using the Spotify API for Python: Spotipy. I can also search in Spotify for my emotion categories to find songs pre-labeled with the target.
- Lyrics Genius API: If the Music Dataset doesn't work out, I can use Spotipy along with this to obtain lyrics.

### What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?

An individual unit of analysis is a song. I will work with lyrics, energy, valence, dancability, loudness, and other features. I will need to cross-reference research on words related to emotions and musical energy/valence related to emotions.

### If modeling, what will you predict as your target?

I will predict one of a number of emotions that describe each song in the test set. I would like to use 4-8 emotional classifications.

# Tools:

### How do you intend to meet the tools requirement of the project?

Modeling will use the python packages for classification models. Storage may use some SQL, processing a large dataset may need some cloud computing, and I'll have to find some interesting plotting methods.

### Are you planning in advance to need or use additional tools beyond those required?

No

# MVP Goal:

### What would a minimum viable product (MVP) look like for this project?

One option is a partial model using just the lyrics (or the musical features). Another option is a full model using only two of the emotions for classification.
