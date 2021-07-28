### Adjustments to proposal
Feedback: Needs a clearer purpose for existing 😑

__What does a user have to gain from this?__
As it is, it's just a very general toolset. More like a feature set. I'd like users to be able to database their digital media assets in such a way that it's __easier to find them__ than with a file browser like Finder (Mac) or Explorer (Windows).

I need to scale down the scope.

#### Idea #1 research
File browsing app
- Keep it simple, it's just a file browser
- For stretch goals, it can store file locations (addresses on a user's specified device, or on the web)
- Users could attach metadata like licenses (for digital assets) and integrity checksums

__Has this been done? What need does this serve?__
- Nice little tutorial: [https://www.youtube.com/watch?v=LT97kQWf7wU](https://www.youtube.com/watch?v=LT97kQWf7wU)
  - Don't like that it's a desktop application. That limits its accessibility. It's also not on-curriculum enough (e.g. not a web app) to be a satisfying capstone demonstration for me.

__File browser web apps?__
- This is awesome: [https://webix.com/filemanager/](https://webix.com/filemanager/)
  - I kinda just want to use this as one feature of my app. It takes all the work out of building something that's PURELY for functionality
  - SCRATCH THAT. It's enterprise-level software that doesn't even have a price tag unless you consult them. Next.
- This looks promising: [https://github.com/filebrowser/filebrowser](https://github.com/filebrowser/filebrowser)
  - It's a web app (yay)
  - Should I just use this as a library/middleware for something bigger in scope and less boring than a file browser? 😕
  - Apache 2.0 license!

__Tech stack__
- JS/CSS/HTML?
  - There's almost nothing left to do if this file browser already exists... I don't want to just install a resource that makes up 75% of my project's code
  - The other 25% would be styling/presentation, and having a database
- Firestore database? MongoDB?

#### Idea #1 conclusion
- I don't think a simple file browser web app has enough __identity__ or __usefulness__
- While the "File Browser" library is insanely nice, and useful, it just leaves too little for me to do
- I could make my own from scratch
  - Resources:
    - [File on MDN](https://developer.mozilla.org/en-US/docs/Web/API/File)
    - [File() on MDN](https://developer.mozilla.org/en-US/docs/Web/API/File/File)
    - [File on W3C](https://w3c.github.io/FileAPI/)
    - [Working with files](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Working_with_files)
    - [IndexedDB API](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API)
- I don't think this is "enough" for me to be happy with it. It's not even a feature, it's just a piece of functionality.
- Give this more "identity"

### Desired tech stack
- HTML5/CSS3
  - I want this to be a __web app__, not something a user needs to install
  - This limits options (which is good) &mdash; I don't want to use a relational database like MySQL because it wouldn't be lightweight enough for a web app
  - Time allowing, I want this damn thing to look GOOD
- React
  - I want the practice, and to have it in my portfolio
- Firebase/Firestore?
  - Definitely the path of least resistance
  - I'm not stoked about Google's [privacy violations and ongoing lawsuit in the state of California](https://en.wikipedia.org/wiki/Firebase#User_privacy_controversies), but... when in Rome
  - Full CRUD

### Desired functionality or features
- Accessible design
- Mobile-first design (stretch)
- Deploy on web
- Deploy as an app (very much stretch)
- User registration, authentication, and authorization
- File browser
  - Adds a link to the file path
    - Only launches if that storage device is connected
    - Still useful if the device is disconnected because it tells a user where their file lives
  - Add links to web addresses (because it's the same as the above, just easier)
  - File browser parses MD5/SHA checksums
    - This allows the app to be a file integrity checker over time, as well (compare your original checksum to a current one to make sure your assets aren't corrupt)
  - Can upload files?
    - __No__, I think this is outside of scope. And some files can be gigantic
- User profiles can show files/assets they have access to
  - example: users can choose to display cool game art assets they've found; other users can follow a link to the asset's web site to add them to their own collection
  - private, user-only, and public visibility of assets
- Users can create __pages__ to share and collaborate
  - __project pages__: this is sounding a like like a GitHub repo concept 😞
  - __asset landing pages__: can add information on a given file in a wiki-like page?
  - __blog posts__: WordPress integration?
- Users can __comment__ on user-created pages (e.g. project pages, blog posts)

### Simple ideas using all of the above

#### Idea #2
- A digital asset manager specifically for tracking licenses on various assets used in projects
  - example: you link two files from your computer to the app -- a pixel-art map with a CC0 license, and a pixel-art character with a GPL2.0 license; the app makes it easy to see the licenses, and possibly warns of conflicts
    - this actually implies creating __project__ pages, or at least having a dedicated table for projects in the database -- many projects (created by users) can have many assets
    - this would also have to implement a file browser... __so shouldn't a user be able to find files/assets based on their license?__ Wouldn't that be useful?
  - the "identity" of this feels too broad. Is this for __any__ licensed digital asset? What user is going to say "oh, nice, I need this"?
    - I don't want to scope this down to a specific type of asset (like game-making assets) because that limits its usefulness, too 😑
    - is this essentially a media browser, like iTunes? But a little more transparent and collaborative about licensing (projects === playlists, essentially?) whereas iTunes enforces DRM (same thing fundamentally)

#### Idea #3
- A Star Wars multimedia database
  - this was one of my original ideas:
    - one simple view/access point could be a __timeline of Star Wars media__ (e.g. reading/watching order)
      - for style, the timeline could have an Easter egg of skewing and turning yellow like the films' opening crawl
      - whole project could be a makeover for [StarWarsTimeline.Net](http://starwarstimeline.net)
    - this could also double as an API for other programmers to use
      - replacing to very incomplete [SWAPI](https://swapi.dev/about) with far more media than just the six films
    - turn into an encyclopedia in the future? (Yodapedia) _Definitely_ outside of scope
  - __I don't really want my capstone to be a weirdly-niche Star Wars showcase__

#### Idea #4
- A more general sci-fi/fantasy database, maybe?
  - looks like [http://www.isfdb.org/](http://www.isfdb.org/) is way ahead of me there
    - leaves a lot to be desired as far as style
    - maybe I could dump this data as a pseudo-API, maybe even create an API from it?
  - this could be handy for tagging passages in novels for easy lookup (e.g. "space battle") for writers
    - tons of use cases for this, how can I dial it in?
    - I really like the idea of being able to "tag" written passages -- I've __never__ found looking up written words to be as accessible and easy as other forms of data. What if you could search your entire ebook library for scenes tagged with "space battle"? How insanely helpful would that be for a writer?
    - this also ties back into [one of my other capstone ideas](https://docs.google.com/spreadsheets/d/1JklQ4uY-ypndcUlLGXwcErMScg4-0UX2_9EomDLTwqM/edit?usp=sharing), which was to have a __database of terms and phrases__
      - these terms/phrases would just be "tagged" (as individual words, or as sentences, passages, etc.)
      - a fiction writer or researcher could have easy access to terms that originated in a text
        - this is really useful for __spell-checking invented words__ and for __conforming to publisher style guides__
      - this database could be a public lexicon API for invented terms
        - easier for me to scope around a specific franchise, like Star Wars... so in this case, this idea is too general
        - and it's been done in the general sense already: [https://sfdictionary.com/](https://sfdictionary.com/)

#### BiblioPile (final idea)
- I just need this project to have some __identity__. I've got a pun, it scopes things down (books only, not all media), and it suggests an aesthetic style (think GoodReads, or libraries)
- A media asset manager for __books__
  - digital books, linked to or at least labeled with the storage devices they live on
  - physical books, labeled to locations (e.g. "home: bedroom bookshelf" or "storage unit")
- Try to implement tagging functionality (stretch)
  - This has __actually__ been done! [Hypothes.is]
    - [https://github.com/hypothesis](https://github.com/hypothesis)
    - [https://via.hypothes.is/https://web.hypothes.is/demos/](https://via.hypothes.is/https://web.hypothes.is/demos/)
    - [https://web.hypothes.is/demos/epubjs/](https://web.hypothes.is/demos/epubjs/)
    - [https://web.hypothes.is/developers/](https://web.hypothes.is/developers/)
    - [https://h.readthedocs.io/en/latest/](https://h.readthedocs.io/en/latest/)
  - How is my idea different?
    - well first off, this is only a stretch goal, so not the main feature (which is users logging/sharing book collections and locations)
    - I kind of want this to be MVP, but I don't think I can pull it off in the time allowed
    - it actually looks like this is fully open info -- but I want users to be able to have the ability to keep tags/books private or visible to other users only
    - REALLY COOL mission for Hypothes.is, but not the use-case I'm going for: [https://hypothes.is/annotating-all-knowledge/](https://hypothes.is/annotating-all-knowledge/q)
- Try to make it look nice
- How do I __not__ make this "Shitty GoodReads"?
  - GoodReads doesn't appear to have any way for users to record where their books live
  - Could also add other metadata, like MD5/SHA checksums or physical condition
  - Users could have blog posts for books (very stretch)
  - I can try to coexist with GoodReads by supporing [importing and exporting their user book collections as CSVs](https://www.goodreads.com/review/import)

### Final proposal (approved)
Name: BiblioPile
 
MVP:
- the user should be able to add physical books to their profile with unique identifiers (e.g. ISBN)
  - book entries may be created by users
  - existing book entries may be added to users’ profiles
- the user should be able to add digital books to their profile (as a list object, not the source binary)
- the user should be able to add devices and physical locations to their profile
  - this allows the user to associate a digital or physical book with its location
  - they can then easily look up where they last stored a book or other document (digital or physical)
- the user should be able to add metadata to books (e.g. storage location, tags/keywords, date acquired, series, reading order, physical condition, MD5/SHA checksums)
- the user should be able to import and export their book lists (compatible with GoodReads CSVs)
- the user should be able to set the public visibility of any books or locations
 
Stretch goals
- the user should be able to create posts associated with a book (e.g. notes to self, public reviews, private GoodReads drafts)
- the user should be able to launch/open digital books based on their recorded location
- the user should be able to highlight and tag content within EPUB and PDF documents by opening them in the browser
- the user should be able to highlight and tag live or locally-stored web pages, and back live pages up on Archive.org
- the user should be prompted to review differences if they create a book entry that may be a duplicate
- the user should be able to click on a book and submit a form to create a plain-text citation from it for use in bibliography
  - all citations are stored for later reference
  - these can be expanded into “fact” objects as a further stretch goal (see below)
- the user can create “facts” by making a concise note on a bibliographic citation linked to a source (i.e. book)
  - facts can be nested (built from one or more other facts)
  - facts must be concise but may have explanatory posts and comments from other users
- the user can import book data from GoodReads or other sites instead of creating entries manually
 
Showcase objectives:
- React frontend
- C# backend
- User authentication and authorization
- Flashy style

### Original proposal (unapproved)
Name of Student:
Patrick Lee
 
Name of Project:
???
 
Project's Purpose or Goal: (What will it do for users?)
Allow users to create accounts for tracking their digital media assets (e.g. ebooks, movies, game-creation assets) and projects that use them. Users can share their media asset libraries as sortable lists on a profile page, which have robust sorting/listing options like “by author,” “by release date,” “by fictional chronology,” etc. — these lists are structurally similar to iTunes playlists; they can be made either manually or procedurally (with a granular search akin to the iTunes “Smart Playlist”). Assets can be mapped to a local directory (private to each user for their own use), which allows two major benefits: easier launching of assets using this app rather than navigating through system folders, and logging hashing checksums (MD5 & SHA1, as well as more secure SHA2) to verify file integrity over time. Assets can also have their licenses tracked, so that users can group them in a list for projects and see all included licenses at a glance.
 
 
List the absolute minimum features the project requires to meet this purpose or goal:
- User registration, authentication, and authorization
- Views:
  - Home page with navigation links and user sign-in elements (read, authenticate)
  - User registration (create)
  - User account settings (update, delete)
  - Project registration and updating (create, update, delete)
  - Public & private versions of user & project profile pages (read, authorize)
  - Public & private user-shared asset “lists” (create, read, authorize)
  - Lists of all assets from multiple users (read)
    - Lists can launch files or open their directories if a user is logged in
    - Lists can link to hosted files
  - User-created landing pages for select assets, like e.g. a movie or movie series (create, read)
- Database(s):
  - Users
    - UUID
    - Authorization level
    - Username
    - Password
    - Real name
    - Email & backup email
    - Links (e.g. GoodReads, GitHub or Twitter profiles)
    - Profile page content or link
    - Assets (imported from asset database?)
    - Asset lists (manual or procedural)
  - Assets
    - UUID
    - Titles and aliases
    - Contributors (author, co-authors, artist, editor, etc.)
    - Other unique identifiers (e.g. ISBN, Library of Congress Control Number, IMDB/GoodReads/other permalinks, data entity ID)
    - License(s)
    - Receipt info, such as price and date of purchase
    - Primary asset category (e.g. “work of fiction,” “work of nonfiction,” “asset collection”  e.g. audio samples)
    - Primary asset type (e.g. “font,” “novel,” “image,” “node module,” “collection (of other assets)”)
    - Parent collections or assets
    - Child collections or assets
    - Source files (file name, checksums, online file locations, local file locations (private), users who have it)
    - Tags and other metadata
  - Projects
    - Are associated with both users (contributing to a project) and assets (used in the project)
    - Landing page content
    - Link to project home page (the landing page, or external, e.g. a GitHub repo) 
  - More stuff
 
What tools, frameworks, libraries, APIs, modules and/or other resources (whatever is specific to your track, and your language) will you use to create this MVP? List them all here. Be specific.
- React with Redux
- ASP.NET Core 5.0 or Firebase
- HTML5/CSS3
 
If you finish developing the minimum viable product (MVP) with time to spare, what will you work on next? Describe these features here: Be specific.
- Views:
  - Flash cards (generated from metadata linked to sources like assets or web articles)
  - Blog posts and articles (possible WordPress integration)
  - Reddit-style commenting and comment-ranking
  - Highlighting and tagging text documents (ebooks, Word docs, PDFs)
- Databases:
  - Glossary of terms and phrases (linked to a project, e.g. fictional names)
  - Flash card sets
 
What additional tools, frameworks, libraries, APIs, or other resources will these additional features require?
???
 
Is there anything else you'd like your instructor to know?
Why do I do this to myself
