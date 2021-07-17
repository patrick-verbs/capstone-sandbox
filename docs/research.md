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
