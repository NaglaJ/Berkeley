There is lots of music data from spotify and others, but interestingly the field that is often missing (NaN) is genre. Genre is often not sufficient to describe a single song, so an additional field called tags exists to include other genres that the song could fall into.
But if Genre is NaN, then it becomes harder to identify other genres to include in tags.  So let’s make sure we can predict the genre for 2 reasons: 
Fill in the data for songs that have not identified a genre–take a guess of what the dominant genre is based on other features
Predict the best genre for musicians to categorize their releases, so that their audience will be reached most efficiently.
The Data:
Dataset: Million Song Dataset + Spotify + Last.fm
Field Descriptions: Field list | Million Song Dataset


Findings(https://github.com/NaglaJ/Berkeley/blob/Capstone/Capstone.ipynb)
My initial approach was to use exclusively song characteristics like beats per minute, valence, instrumentalness, etc., to predict a genre.  As you can see from the definitions below for genre there is not scientific approach to the categorization.  This approach yielded only a 54.5% accuracy using RandomForrestClassifier.
My next approach will include additional data/features, specifically date of the song (my theory is that the older songs fell more neatly into a category) and tags which include several genres and characteristics included in the song.

Genre Reference Information
Music genres are categorized based on shared characteristics like rhythm, melody, instrumentation, cultural origin, and lyrical content. While there are many ways to classify music, here are some of the most common music genre categories, along with brief definitions:
1. Pop
Definition: Short for "popular music," pop is characterized by catchy melodies, simple structures, and lyrics that often focus on love, relationships, and emotions.


Characteristics:


Strong hooks and choruses.


Radio-friendly length (usually around 3-5 minutes).


A broad appeal to a wide audience.


Examples: Taylor Swift, Ariana Grande, Ed Sheeran.


2. Rock
Definition: Rock music is defined by its use of electric guitars, bass, drums, and strong rhythms. It originated in the late 1940s and early 1950s.


Characteristics:


Focus on guitars (electric and acoustic).


Drums and bass are central to the rhythm.


Lyrics often focus on personal or societal issues.


Subgenres: Classic rock, alternative rock, punk rock, indie rock.


Examples: The Beatles, Queen, Nirvana, Foo Fighters.


3. Hip Hop / Rap
Definition: Originating from African American and Latino communities in the 1970s, hip hop is defined by its rhythm-based, lyrical style known as rap, along with DJing, beatboxing, and breakdancing.


Characteristics:


Rhythmic vocal delivery (rap).


Sampling of other songs or sounds.


Heavy use of bass and drums.


Subgenres: Trap, boom bap, gangsta rap, conscious rap.


Examples: Kendrick Lamar, Kanye West, Drake, Tupac.


4. Electronic Dance Music (EDM)
Definition: A broad category that includes any music created primarily with electronic devices, often produced for dancing in clubs or festivals.


Characteristics:


Synthesizers, drum machines, and computer-based production.


Focus on beats and rhythm for dancing.


Build-ups, drops, and breakdowns are common.


Subgenres: House, techno, dubstep, trance, drum and bass.


Examples: Calvin Harris, Skrillex, Marshmello.


5. R&B (Rhythm and Blues)
Definition: Originating in African American communities, R&B combines jazz, blues, and gospel influences with a strong emphasis on rhythm and soulful vocals.


Characteristics:


Smooth, emotional vocals.


Strong emphasis on rhythm, especially with bass and drums.


Lyrically focused on love, relationships, and emotional expression.


Subgenres: Contemporary R&B, soul, neo-soul.


Examples: Beyoncé, Usher, Alicia Keys.


6. Jazz
Definition: Developed in the early 20th century, jazz combines elements of African rhythms with European harmonic structures. It emphasizes improvisation and intricate instrumentation.


Characteristics:


Complex rhythms and harmonies.


Improvisation is key.


Use of instruments like saxophones, trumpets, piano, and double bass.


Subgenres: Bebop, swing, smooth jazz, fusion.


Examples: Miles Davis, John Coltrane, Duke Ellington.


7. Country
Definition: Country music blends folk, Western, and blues traditions. It's deeply tied to rural American culture and often features storytelling lyrics.


Characteristics:


Use of guitars, banjos, fiddles, and harmonicas.


Lyrics often reflect themes of love, loss, and life in rural areas.


Clear, simple song structures.


Subgenres: Traditional country, modern country, bluegrass, outlaw country.


Examples: Johnny Cash, Dolly Parton, Luke Bryan.


8. Classical
Definition: Rooted in the Western art music tradition, classical music spans a long history from the medieval period to the present, with a focus on orchestral compositions.


Characteristics:


Complex compositions with orchestral or chamber arrangements.


Use of symphonies, concertos, sonatas, and operas.


Ranges from highly structured and formal to more experimental.


Examples: Ludwig van Beethoven, Wolfgang Amadeus Mozart, Johannes Brahms.


9. Blues
Definition: Originating in the Deep South, blues music is a genre that focuses on expressing emotional experiences, especially pain, through a distinctive 12-bar structure and “blue” notes.


Characteristics:


Simple, repetitive chord progressions.


Use of call-and-response vocals and guitar licks.


Lyrically focuses on struggle, pain, and heartache.


Examples: B.B. King, Muddy Waters, Robert Johnson.


10. Reggae
Definition: Emerging from Jamaica in the late 1960s, reggae blends ska, rocksteady, and African rhythms with a focus on social and political themes.


Characteristics:


Syncopated rhythms, often with a "one-drop" drum pattern.


Emphasis on bass lines and offbeat guitar or piano.


Lyrical themes often focus on love, unity, and resistance.


Examples: Bob Marley, Peter Tosh, Jimmy Cliff.


11. Folk
Definition: Folk music is a genre that includes traditional and contemporary music tied to specific cultures, often passed down orally.


Characteristics:


Acoustic instrumentation (guitar, banjo, fiddle, etc.).


Storytelling lyrics that reflect social issues, history, or personal experiences.


Examples: Bob Dylan, Joan Baez, Mumbo Gumbo.


12. Alternative / Indie
Definition: Alternative music (also known as indie) refers to non-mainstream music that blends a variety of genres, often challenging traditional song structures and sounds.


Characteristics:


Diverse instrumentation and experimental sounds.


Lyrically introspective or abstract.


Often released by independent labels.


Examples: Radiohead, The Strokes, Vampire Weekend.


13. Metal
Definition: Metal is a subgenre of rock that emphasizes heavy, distorted guitars, complex structures, and intense or dark themes.


Characteristics:


Distorted guitar riffs, fast tempos, and heavy drums.


Often themes of fantasy, rebellion, or personal struggle.


Vocal styles can range from clean singing to harsh growling or screaming.


Subgenres: Heavy metal, thrash metal, death metal, black metal.


Examples: Metallica, Iron Maiden, Slipknot.


14. World Music
Definition: World music is an umbrella term for music that originates from non-Western cultures, incorporating traditional sounds and instruments from around the globe.


Characteristics:


Use of traditional instruments like sitar, djembe, or marimba.


Fusion of indigenous rhythms and melodies with contemporary styles.


Examples: Ravi Shankar, Youssou N'Dour, Cesária Évora.


15. Punk
Definition: Punk is a fast, loud, and rebellious genre that emerged in the mid-1970s. It’s defined by its DIY ethos and opposition to mainstream culture.


Characteristics:


Short, fast songs with simple structures.


Raw, distorted guitars and politically charged lyrics.


Emphasis on attitude and anti-authoritarian themes.


Examples: The Ramones, Sex Pistols, Green Day.



These are just some of the major categories, and many artists blend different genres to create unique sounds. Some genres, like pop or rock, have a broad range of subgenres that make them highly adaptable to different eras and cultural influences.
Yes, some music genres are definitely more lucrative than others, especially when it comes to factors like mainstream popularity, global appeal, streaming revenue, live performance income, and record sales. However, profitability can vary depending on the artist, market, and business strategies used. Here's a breakdown of how certain genres compare in terms of potential earnings:
1. Pop
Most Lucrative: Pop is arguably the most commercially successful genre worldwide.


Reasons:


Broad appeal across different age groups and cultures.


High streaming numbers and airplay on mainstream radio.


Huge potential for brand deals, merchandise, and tours.


Major artists in pop (e.g., Taylor Swift, Ariana Grande) rake in hundreds of millions through album sales, concert tours, and endorsements.


Example Earnings: A pop artist’s world tour or album release can generate tens of millions of dollars, with a strong revenue stream from merchandising and licensing.


2. Hip Hop / Rap
Very Lucrative: Hip hop/rap is one of the top genres in terms of streaming numbers, especially in younger demographics.


Reasons:


Strong streaming dominance, particularly on platforms like Spotify and Apple Music.


A culture of celebrity and influence, with artists often extending into fashion, social media, and other industries.


Lucrative partnerships, brand endorsements, and collaborations with other high-profile figures.


Example Earnings: Artists like Kanye West, Jay-Z, and Drake generate substantial income from album sales, tours, fashion lines, and business ventures.


3. Electronic Dance Music (EDM)
Highly Profitable: EDM has grown into a global phenomenon, especially in festival and club scenes.


Reasons:


Major money comes from high-ticket festivals (like Tomorrowland, Ultra) and exclusive nightclub gigs.


Top DJs (e.g., Calvin Harris, David Guetta) can earn millions per performance and rake in millions in annual income.


EDM has a global fanbase, and music festivals generate massive revenue, sometimes in the hundreds of millions.


Example Earnings: High-profile DJs can make up to $1 million per show, plus substantial revenue from streaming, album sales, and merchandise.


4. Rock
Lucrative, But Varied: Rock has seen a decline in mainstream popularity, but it still remains highly profitable for legacy bands and well-established acts.


Reasons:


Profitable concert tours are a primary income source for rock artists, especially for those with a loyal fan base (e.g., The Rolling Stones, Foo Fighters).


Rock festivals like Lollapalooza and Glastonbury attract huge crowds and generate significant income.


Merchandise, album sales (though less prominent today), and brand partnerships are additional revenue streams.


Example Earnings: Big rock acts can gross tens of millions from global tours, with additional earnings from merchandise and special-edition album releases.


5. R&B
Moderately Lucrative: While not as universally dominant as pop, R&B remains profitable, especially for artists who blend R&B with other genres like pop or hip hop.


Reasons:


R&B artists (e.g., Beyoncé, Usher) have significant mainstream appeal and command high ticket sales for live shows.


Streaming platforms are particularly friendly to R&B, as the genre has a strong presence in playlists.


Example Earnings: Major R&B artists can make substantial income through music sales, touring, merchandise, and brand partnerships (e.g., Beyoncé's Ivy Park with Adidas).


6. Country
Very Lucrative (Especially in North America): Country music, particularly in the U.S., is a big money-maker, especially for touring and merch sales.


Reasons:


Country festivals and concerts often sell out, and country music has a loyal fan base.


Country artists make significant revenue from album sales, streaming, and brand deals.


Example Earnings: Stars like Luke Bryan, Taylor Swift (early career), and Garth Brooks are known to generate tens of millions from albums, tours, and partnerships with brands like Wrangler or Ford.


7. Jazz, Blues, Classical
Less Lucrative: These genres are more niche compared to pop or hip hop. While they have dedicated audiences, they generally don’t generate the same level of mainstream success.


Reasons:


Limited commercial appeal compared to pop or hip hop.


Revenue often comes from live performances, royalties, and specialized sales (e.g., jazz festivals, classical concerts).


Classical and jazz artists tend to perform in smaller venues or for more exclusive audiences.


Example Earnings: Classical and jazz musicians can still earn well through performances, especially if they play in prestigious venues or work with orchestras. But compared to pop or hip hop stars, the overall earnings are often lower.


8. Metal
Moderately Lucrative: Metal has a strong but niche fan base. While it’s not as commercially successful as pop or hip hop, metal bands still make decent earnings, particularly through tours and merchandise.


Reasons:


Metal festivals and live shows are major revenue drivers, though the audience is typically smaller than that of pop or EDM.


Band merchandise is a key revenue stream for metal acts.


Example Earnings: Successful metal bands (e.g., Metallica, Iron Maiden) can earn tens of millions annually from tours and merchandise sales.


9. Reggae and Folk
Less Lucrative: While these genres have loyal audiences, they tend to be more focused on smaller, regional markets and have less mainstream appeal.


Reasons:


Reggae and folk often appeal to specific cultural or niche groups.


Revenue typically comes from live shows, smaller-scale festivals, and regional record sales.


Example Earnings: Bob Marley is a major exception in reggae, where his legacy has made him a global brand. Folk music tends to have a cult following but not the commercial scale of pop or hip hop.


10. Punk / Indie
Less Lucrative: While indie and punk music is beloved for its authenticity and passion, these genres are typically not as financially rewarding for most artists unless they break through to mainstream success.


Reasons:


The DIY nature of these genres means smaller budgets for tours, recordings, and promotion.


However, successful indie and punk acts (e.g., Arcade Fire, Green Day) can generate significant revenue, especially from live shows and merchandise.


Example Earnings: While most indie bands earn modestly, those who find success in streaming and touring can make millions. Green Day, for instance, has generated massive earnings through touring and album sales.



Conclusion:
Pop, Hip Hop, and EDM are the clear leaders in terms of global revenue potential.


Rock, R&B, and Country also generate substantial income but often rely more heavily on live performances and legacy status.


Jazz, Blues, Classical, and Indie tend to be less lucrative overall, although certain acts in these genres can still earn a comfortable living, especially through touring, teaching, and niche markets.


Genres with broader mainstream appeal tend to be more lucrative due to larger audiences, more widespread streaming, and greater commercial opportunities in areas like advertising, fashion, and film.

