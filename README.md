# website

## Initial Setup
A good way to edit the website content is to use **Visual Studio Code** (download [here](https://code.visualstudio.com/download)), but [other options](https://docs.hugoblox.com/getting-started/cms/) work too. RStudio + Blogdown package used to be a good option, but it no longer plays as nicely with Hugo - I'd recommend using one of the other approaches.

To setup a website and begin editing in VS Code:
1. Install Hugo Extended following instructions [here](https://docs.hugoblox.com/getting-started/install-hugo/). *Note*: if you are using Windows and your system is reasonably modern, the Powershell you have probably works fine, no need to install a new variant.
2. Clone a template to your local computer. We're using [HugoBlox/theme-research-group](https://github.com/HugoBlox/theme-research-group). If you are looking to make a personal website, [HugoBlox/theme-academic-cv](https://github.com/HugoBlox/theme-academic-cv) may be a good option. More options [here](https://hugoblox.com/templates/). Rename the directory as you wish.
3. In VS Code, replace the README.md and content in the `content`, `assets/media`, and `images` directories with your materials, as described below. Additional details on customization [here](https://docs.hugoblox.com/getting-started/customize/).
4. As you edit, view the rendered site locally by running this command in the VS Code terminal (or other terminal, e.g. GIt Bash): `hugo server -D`. It will return a message that includes a link (e.g., `http://localhost:1313/`) that you can open in your browser. As the message indicates, kill the server via `Ctrl + C`. 
5. On GitHub, create a repo for your website. On your local machine, add the remote repo via `git remote add origin <url>`

## Quick Orientation
Once installed, the main website files that get modified are in the top level `content`, `assets/media`, and `images` directories.

### content
The home page is controlled by the `_index.md` file here. Any photos that you want to appear on the home page can either go here or in `assets/media` (I think).

#### content/authors (aka Lab Members)
To **add a new person** to the group:
1. Copy the directory from a similar group member under the `content/authors` directory 
2. Change the name of the directory, using dashes as spaces between first/last name and middle initial (if desired), e.g.: `carolyn-b.-voter` or `omowumi-erukubami`
3. Replace `avatar.jpg` with a photo of the new person. Be sure to keep the name of this photo `avatar.jpg` (or `.png` or `.webp`, I think).
4. Update `_index.md` with the information for the new person.

**Social icon** options that may be relevant include:
- *Email.* icon: envelope, icon_pack: fas
- *Website.* icon: globe, icon_pack: fas
- *Orcid.* icon: orcid, icon_pack: ai
- *Google Scholar.* icon: google-scholar, icon_pack: ai
- *GitHub.* icon: github, icon_pack: ai
- More icon options here:
	- fab: https://fontawesome.com/icons?d=gallery&s=brands
	- fas, far: https://fontawesome.com/icons?d=gallery&s=regular,solid
	- ai: https://jpswalsh.github.io/academicons/

#### content/doc
If you want to reference a PDF or other document in a page (e.g., your CV, see Carolyn's "author" profile as an example), upload it here. 

Note that publications have a different process - see details below.

### content/event (aka Presentations)
To add a presentation:
1. Copy the directory from a similar event under the `content/event` directory. Grab one from the same conference, if that is a choice.
2. Change the name of the directory using the format `YYYY_MM_Conference_FirstAuthorLastName`
3. Replace `featured.jpg` (or `.png` or `.webp`) with the logo of the conference/venue, if different from the template event you copied.
4. Update `index.md` with the information for the presentation. 
    - authors: For lab members, be sure to list the full name exactly as it appears in `Authors` (i.e., check if middle initial is used). For non-lab members, list the name the same way it appears previously on the site (in other presentation or publications).
	- event_url: link to the conference program, if possible (and a semi-permanent link)
	- summary: specify Poster, Talk, Invited Talk, or Lightning Talk
	- project: use dashes to list any projects associated with this publication. The name of the project to use is its directory name (i.e., `YYYYProjectStarted_ShortName`).

### content/people
This directory (`content/people`) contains just an `index.md` file which controls the appearance (sorting and grouping) of the `People` page. To add a new lab member, don't adjust anything here - instead, see `Authors` above.

### content/project
To add a project:
1. Copy the `blank` directory under the `content/project` directory.
2. Change the name of the directory to `YYYYProjectStarted_ShortName`.
3. Add an icon with the filename `featured.png` (or `.jpg` or `.webp`)
4. Add project info to `index.md`.

### content/publication (aka Papers)
To add a publication:
1. Copy the directory from a similar paper under the `content/publication` directory.
2. Change the name of the directory to `lastnamefirstauthor-YYYY-first-three-words`
3. Replace the pdf with a pdf of the publication you are adding. I think this file can be named anything, but if something isn't working, try making the name of the pdf the same as the name of the directory.
4. Replace `cite.bib` with a bib file that contains the appropriate citation for the publication in question. Generate this in Zotero by right clicking on the publication name in Zotero > Export Item > Format: Better BibTeX > save file as `cite.bib` and copy to the publication directory.
5. Update `index.md` with the information for the publicaton. Be careful to preserve quotation marks where they exist - they can matter here.
	- title: use single quotes around title, in case there are any special characters
	- authors: For lab members, be sure to list the full name exactly as it appears in `Authors` (i.e., check if middle initial is used). For non-lab members, list the name the same way it appears previously on the site (in other presentation or publications).
	- date: this is the date (`'YYYY-MM-DD'`) that the publication was published
	- publishDate: doesn't matter, leave as-is
	- publication_types: options include article-journal, report, or paper-conference
	- summary: Journal Article, Conference Paper, or Report
	- publication: use single quotes and italics around the publication name
	- doi: no quotes, just the number
	- project: use dashes to list any projects associated with this publication. The name of the project to use is its directory name (i.e., `YYYYProjectStarted_ShortName`).
	- abstract: use single quotes around this.