# Divinity Original Sin 2 UA localization

Divinity: Original Sin II is a role-playing video game developed and published by Larian Studios.
It could be the best CRPG on the market with only few flaws. One of the disadvantages is the lack of Ukrainian localization.
The lexical similarity of the Russian and Ukrainian languages is 62%.

# Localization files structure
There are few files inside the language folder. It was unpacked from the `*.pak` file from the game files.

'russian.xml' is a simple xml that contains almost all the lines that we have, including menu, interface and dialogues.
Each `content` tag is a separate string that contains text and unique `contentuid`. Those ids are connected with dialogues,
menu and interface structure that you could find inside `Game.pak` and `Origins.pak`. So it helps to understand the context for each string.

`Gender` folder and `russian_to_F.xml` file is a gender specific translation. In our case it's the situation when player is female.

# Packing and unpacking *.pak files 
To extract or pack some game files back you will need to have an export tool. Read more and download it here - https://docs.larian.game/Pak_Extractor_Guide
![image](https://user-images.githubusercontent.com/55234934/188365166-7be2e199-05ad-42b4-9c5c-bbf98f9de868.png)

There are also some tools that could be used for working with dialogues and other stuff, but I didn't manage to figure out yet, cause I was ok with my regular IDE.

# Translation process
I hand-translated about a thousand and a half lines and realized that it was too tedious. Mostly, it were some menu and interface trandlations.
After this, I used the Google translate API to translate all the lines from the `russian.xml` file. Previosly I have collected manually translate
lines to exclude it and shorten the amount of requests to translate API. And I've collected all the duplicates with the same purpose. With this
approach I've avoided about 10k of redundant requests.

You can see the result inside `russian.json` file. I'm going to refine the translation here and then parse it and occupy the xml file with
translated lines. 
