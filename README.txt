LEFTERIS KRYSALIS: WEBSITE (plain HTML draft)

To look at it: unzip the folder and double-click index.html. It opens in
your browser, no internet or server needed.


WHAT IS IN THE FOLDER

index.html        the front page: your name and the list of all works
cv.html           the CV as a web page
cv.pdf            the CV as a download
impressum.html    empty for now; not linked yet (see below)
style.css         all colours, type and layout, in one place
works/            one HTML file per work
works/_template.html   a blank work page to copy for new works
images/           all pictures
audio/            MP3s that used to live inside WordPress (see below)


STILL TO DO

1. Audio: the three MP3s from WordPress are in audio/ under their original
   names, and the pages point to those names. GitHub's website upload
   refuses single files over 25 MB; such a file goes to Internet Archive
   instead (see AUDIO below).

2. Some pages have hidden boxes ("To fill in: ...") waiting for your text,
   images and links: Hydraulic Border Intervals, Synoriaka Echωtopia,
   E85 Echotopia of a borderscape, Aphonic Echotopia (FLUTEN), the Clipping 4 essay,
   the photo boxes on Hydraulic Border Intervals, Synoriaka Echωtopia and Hydra,
   and the Graz teaching page.
   They are hidden on the site; to see them, see the note in style.css.
   When you fill one, delete the whole line <p class="gap">...</p>.

3. The images come out of the portfolio PDF and are small. Replacing them
   with your original photos (same file name, in images/) makes them sharp.


HOW TO ADD A NEW WORK

1. In works/, copy _template.html and rename the copy, e.g.
   works/my-new-work.html  (lowercase, hyphens, no spaces).
2. Open it in a text editor and replace the example text:
   the <title>, the category in the path line, the <h1> title,
   the lines in "meta", the paragraphs, the image, the links.
   Each paragraph is one <p>...</p>. Each link is one <li>...</li>.
   If there is no image or no audio, delete that line.
3. Put its image in images/ (and MP3s in audio/).
4. Open index.html, find the category (e.g. <section class="cat" id="installations">)
   and copy one existing line inside it, like:
   <li><a href="works/my-new-work.html"><span class="yr">2027</span><span class="t">My New Work</span><span class="v">Institution</span></a></li>
5. Optionally add a line to cv.html in the same way.


ADDING A PHOTO TO A PAGE

1. Put the photo into images/, e.g. images/synoriaka-1.jpg
   (lowercase, hyphens, no spaces; about 1600 pixels wide is plenty).
2. Open the work page, find the dashed box line <p class="gap">To fill in: ...</p>
   in the right-hand column and replace it with one line per photo:
   <figure><img src="../images/synoriaka-1.jpg" alt="Short description of the photo" loading="lazy"><figcaption>© Name of photographer</figcaption></figure>


WHEN AN UPCOMING WORK HAS HAPPENED

Remove "(upcoming)" from the <title>, the <h1> on its page, and its line in
index.html. Then add text, photos and links on that page like any other.


AUDIO: LINKING OR EMBEDDING FROM OTHER PLACES

Audio files are big, so it is better to keep them on Internet Archive,
Bandcamp, SoundCloud etc. and only point to them from the site.
Put the line in the right-hand column of the work page, inside
<ul class="links"> ... </ul>.

a) Simple link (works for anything: Bandcamp, SoundCloud, radio archives):
   <li><a href="https://the-full-address">Name of the recording</a></li>

b) Player on the page, with the file on Internet Archive:
   - upload the MP3 on archive.org ("Upload"), wait until it is processed;
   - on the item page, under "Download options", right-click the MP3 link
     and copy the address. It looks like
     https://archive.org/download/your-item-name/your-file.mp3
   - use it in the player line:
   <li class="audio"><span>Name of the recording</span><audio controls preload="none" src="https://archive.org/download/your-item-name/your-file.mp3"></audio></li>
   (The Echotopia and Caminata pages already have this line; only replace
   the part inside src="...".)

c) Bandcamp player: on the Bandcamp track or album page click
   "Share / Embed" > "Embed this album", choose a style, copy the code
   (it starts with <iframe) and paste it as:
   <li class="embed">PASTE THE IFRAME CODE HERE</li>
   Note: an embedded Bandcamp or SoundCloud player loads from their servers
   when someone opens the page, so it belongs in the privacy statement later.
   A simple link (a) does not.


IMPRESSUM

impressum.html exists but is empty. When it is filled, add this line to the
footer of the pages, next to the CV link:
  <p><a href="impressum.html">Impressum</a></p>   (from inside works/: ../impressum.html)


CHECKING HOW IT LOOKS ON A PHONE (before putting it online)

Open index.html in Chrome or Firefox on the computer and switch on the
phone view: Firefox: Tools > Browser Tools > Responsive Design Mode
(Cmd+Option+M on a Mac). Chrome: View > Developer > Developer Tools, then the
small phone/tablet icon at the top left of the panel. Pick an iPhone or
Android size at the top and click through the site as normal.


PUTTING IT ONLINE WITH GITHUB PAGES

1. Make a free account on github.com and create a new public repository,
   e.g. "website".
2. On the repository page choose "Add file" > "Upload files" and drag in
   everything that is inside this folder (not the folder itself).
3. Settings > Pages: under "Branch" choose "main" and "/ (root)", save.
   A minute later the site is live at  yourname.github.io/website
4. Settings > Pages > Custom domain: enter eleftherioskrysalis.info.
   GitHub shows which DNS records to add. Add them in the domain settings
   at WordPress.com (Domains > eleftherioskrysalis.info > DNS records).
   When it works, tick "Enforce HTTPS".
5. Later edits: open any file on github.com, click the pencil icon, change
   the text, "Commit changes". The site updates by itself.
