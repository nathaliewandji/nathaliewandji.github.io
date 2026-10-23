**Nathalie Wandji**  
Source of the Nathalie Wandji website, in French and English, built with [MkDocs Material.  
   
 GitHub rebuilds and publishes the site automatically every time a file changes on the main branch.](https://squidfunk.github.io/mkdocs-material/ "https://squidfunk.github.io/mkdocs-material/")  
**Put it online (once)**  
1. Create a **public** repository named <your-username>.github.io.  
2. Upload **all** the files and folders, including the hidden .github folder (see below).  
3. **Settings → Pages → Build and deployment → Source: GitHub Actions.**  
4. Open the **Actions** tab: the "Publier le site" job runs for about a minute. When it shows a green tick, the site is online.  
5. In mkdocs.yml, replace lucy in site_url with your username.  
**The hidden ** **.github** ** folder:** on a Mac, Finder hides folders whose name starts with a dot, so they may not be uploaded.  
   
 If the Actions tab stays empty, create the file by hand on GitHub: **Add file → Create new file**, name it  
   
 .github/workflows/publier.yml, paste the content of that file, and commit.  
**How the site is organised**  
mkdocs.yml                 Settings: name, colours, languages, YouTube link  
 docs/  
   index.fr.md              Home page in French  
   index.en.md              Home page in English  
   a-propos.fr.md / .en.md  About page  
   maths/                   Hub: one folder per level  
     maternelle/            Nursery (writing slates)  
     primaire/  
     form-1/ … form-5/      6e … Seconde  
     lower-sixth/           Première  
     upper-sixth/           Terminale  
     university-1/ … -3/  
   python/                  Hub: one folder per sub-series  
     defi-10-minutes/  
     data-science/  
     statistiques/  
     scraping/  
   tech/  
   elearning/  
   
**Every page exists twice, side by side:** page.fr.md (French) and page.en.md (English).  
   
 If the English file is missing, the French page is shown instead, so you can translate later.  
**Everyday tasks**  
**Add an episode**  
Create two files in the sub-series folder, for example in docs/python/defi-10-minutes/:  
- jour-01.fr.md  
- jour-01.en.md  
It appears in the menu automatically, sorted by file name (jour-01, jour-02…). Template:  
# Jour 1 : afficher un message  
   
 <!-- Paste the YouTube link when the video is out -->  
 [Voir la vidéo](https://youtu.be/XXXX){ .md-button .md-button--primary }  
   
 ## Le code  
   
 ```python  
 print("Bonjour !")  
 ```  
   
 ## Exercice  
   
 Affichez votre prénom.  
   
 ??? success "Solution"  
     ```python  
     print("Lucy")  
     ```  
   
Then, in the sub-series index.fr.md, you can turn the line Jour 1 … <span class="bientot">Bientôt</span>  
   
 into a link: [Jour 1 : afficher un message](jour-01.md).  
**Add a simulation to a level**  
1. Put the .html file in the level folder, e.g. docs/maths/form-2/symetrie-axiale.html.  
2. In that level's index.fr.md and index.en.md, add a card. Copy an existing card from  
 docs/maths/upper-sixth/index.fr.md and change the title, text and file name.  
**Add a sub-series or a level**  
1. Create a folder, e.g. docs/python/automatisation/, with index.fr.md and index.en.md inside.  
2. Add the folder name to the .pages file of the parent folder, at the position you want in the menu.  
3. Add a card for it on the hub page (docs/python/index.fr.md and .en.md).  
4. To show a nicer name in the menu, add a line under nav_translations in mkdocs.yml.  
**Add the YouTube channel**  
In mkdocs.yml, remove the # in front of the three social: lines and put your channel address.  
   
 The YouTube icon then appears at the bottom of every page, in both languages.  
**Useful syntax**  
| | |  
|-|-|  
| **You write** | **You get** |   
| **bold** | **bold** |   
| ```python … ``` | coloured Python code with a copy button |   
| !!! tip "Astuce" + indented text | a coloured box |   
| ??? success "Solution" + indented text | a box that opens on click |   
| $x^2 + 1$ | a maths formula |   
| [text](other-page.md) | a link to another page |   
   
**Rules**  
- **Never rename or move a published page**: links in your videos would break.  
- File and folder names: lowercase, no spaces, no accents, hyphens between words.  
- Everything in this repository is public. Never put student names or data in it.  
