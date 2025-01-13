# Architects Lyrics Corpus
This repository contains a corpus of song lyrics by the British metalcore band Architects. 

### Corpus Description
The Architects Lyrics Corpus is a collection of song lyrics from Architects' discography, 
spanning 10 full albums. It serves as a resource for anyone interested in analysing lyrical themes,
linguistic patterns, stylistic evolution over time, etc., of Architects' lyrics. 

### Text Selection Criteria
The corpus includes lyrics from all officially released studio albums by Architects as available on major streaming platforms, excluding:
- The album *For Those That Wish To Exist At Abbey Road* (2022),
  since this is a different rendition of the same songs on the original *For Those That Wish To Exist* (2021) album,
  which is already included in the corpus.
- Instrumental songs, bonus tracks, and deluxe edition songs.

### Data Collection process
Lyrics were collected per album from three different online lyric databases:
- [Dark Lyrics](http://www.darklyrics.com/a/architects.html ) for the first 8 albums.
- [Metal Kingdom](https://www.metalkingdom.net/album/architects-for-those-that-wish-to-exist-144830)
  for the second-to-latest album included in the corpus (*For Those That Wish To Exist*, 2021)
- [Rockalyrics](https://www.rockalyrics.com/m/565-6854/architects/the-classic-symptoms-of-a-broken-spirit-lyrics)
  for the latest album included in the corpus (*the classic symptoms of a broken spirit*, 2022)

### Cleaning and Preprocessing
Since the lyrics were retreived per album, the lyrics were processed so that each individual song lyric
is stored in its own separate text file. Additionally, extra lines in each file were replaced with spaces.

### Annotations
The corpus includes several layers of linguistic annotations processed using [spaCy](https://spacy.io/):
- **Tokens:** A list of individual words and punctuation marks from the original formatted lyrics.
- **Lemmas:** A list of lemmatised tokens, where each word is reduced to its base form.
- **Part-of-Speech (POS) Tags:** Each token is assigned a detailed POS tag indicating its grammatical category.
- **Named Entity Tags:** Each word/phrase recognised as a named entity, is assigned a Named Entity tag indicating its category.

### File Formats
#### Notebook (.ipynb)
- The file `code.ipynb` contains all code used to realise this corpus, including a short POS analysis.
  
#### Text files (.txt)
- The directory `data/albums` contains text files for the lyrics of each album.
- The directory `data/txt_lyrics` contains individual text files for each song's lyrics, named in the format:
  `album_song#.txt`

#### CSV file (.csv)
- The file `Architects_Lyrics_with_spaCy_tags.csv` contains the fully annotated corpus:

    **Rows:** each row contains data on a song lyric.

    **Columns** (variables):

  | Header | Description |
  | ------ | ----------- |
  | `filename` | The filename of the song lyric file |
  | `title` | The songtitle |
  | `album` | The album the song is on|
  | `year` | The year the album with the song was released |
  | `text` | The song lyric in its original form |
  | `doc` | The doc object of the processed song lyric (casefolded and punctuation removed) |
  | `tokens` | The tokenised version of the song lyrics' doc object |
  | `lemmas` | The lemmatised version of the song lyrics' doc object |
  | `POS` | The Part-of-Speech tags of the song lyrics' doc object |
  | `Named_Entities` | The Named Entity tags recognised in the song lyrics' doc object |
  | `NE_Words` | The words recognised as Named Entities |

### Additional Information
This corpus is provided for non-commercial, research purposes only. 
All rights to the lyrics belong to Architects and their publishers.
