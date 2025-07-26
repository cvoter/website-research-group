# website-research-group

This website is currently hosted at [https://cvoter.github.io/website-research-group/](https://cvoter.github.io/website-research-group/), but I am in the process of transferring the domain to www.carolynbvoter.com. 

## Initial Setup
A good way to edit the website content is to use **Visual Studio Code** (download [here](https://code.visualstudio.com/download)), but [other options](https://docs.hugoblox.com/getting-started/cms/) work too. RStudio + Blogdown package used to be a good option, but it no longer plays as nicely with Hugo - I'd recommend using one of the other approaches.

To setup a website and begin editing in VS Code:
1. **Install Hugo Extended** following instructions [here](https://docs.hugoblox.com/getting-started/install-hugo/). *Note*: if you are using Windows and your system is reasonably modern, the Powershell you have probably works fine, no need to install a new variant. But you may need to install Scoop as described.
2. **Clone a template** to your local computer. We're using [HugoBlox/theme-research-group](https://github.com/HugoBlox/theme-research-group). If you are looking to make a personal website, [HugoBlox/theme-academic-cv](https://github.com/HugoBlox/theme-academic-cv) may be a good option. More options [here](https://hugoblox.com/templates/). Rename the directory as you wish.
	- Note that after cloning with this approach, your remote will point to the HugoBlox repository until you update it. Check this with `git remote -v`.
	- Create a corresponding (but empty) repository for your website on GitHub.
	- Update the remote on your local machine to point to your new repository via `git remote set-url origin <url>`. 
3. **Customize content** in VS Code. Replace the README.md and content in the `content`, `assets/media`, and `images` directories with your materials, as described below. Additional details on customization [here](https://docs.hugoblox.com/getting-started/customize/).
4. **View the rendered site** locally as you edit by running this command in the VS Code terminal (or other terminal, e.g. GIt Bash): `hugo server -D`. It will return a message that includes a link (e.g., `http://localhost:1313/`) that you can open in your browser. As the message indicates, kill the server via `Ctrl + C`. 
5. **Create a GitHub Pages website** using your GitHub repository, once you are ready to go live.
	- Make sure your repository is public. (Creating pages from a private repository is currently a paid feature).
	- Update the `baseURL` in `config/_default/hugo.yaml` with what your github.io address will be. Should be `https://yourusername.github.io/yourreponame'.
	- Add a GitHub workflow to publish your website with each push action. You should already have this under `.github/workflows/publish.yaml`, but make sure your version matches the latest in the HugoBlox template you used (e.g., [HugoBlox/theme-research-group version](https://github.com/HugoBlox/theme-research-group/blob/main/.github/workflows/publish.yaml)). If it's been a while since you initially cloned the template, sometimes the module versions in this file need to be updated.
	- Under your repository Settings > Pages, ensure the build and deployment source is GitHub Actions. Either push a recent commit to activate or go to Actions, select the "Deploy website to GitHub Pages" workflow, and run the workflow manually.
	- Once this runs successfully, you should see your website (live!) at `https://yourusername.github.io/yourreponame'

## Quick Orientation
Once created, the main website files that get modified are in the top level `content`, `assets/media`, and `images` directories.

### content
The home page is controlled by the `_index.md` file here. Any photos that you want to appear on the home page can either go here or in `assets/media` (I think).

### content/authors (aka Lab Members)
To **add a new person** to the group:
1. Copy `content/authors/blank` and rename to the new person. Use dashes as spaces between first/last name and middle initial (if desired), e.g.: `carolyn-b.-voter` or `omowumi-erukubami`
2. Update `_index.md` with the information for the new person.
3. Upload a headshot and name it `avatar.jpg` (or `.png` or `.webp`).
4. Add the person to relevant project(s), if they are not already included. If they have been on publication(s) and/or presentation(s), be sure they are listed (the same) there as well.

**Social icon** options that may be relevant include:
- *Email.* icon: envelope, icon_pack: fas
- *Website.* icon: globe, icon_pack: fas
- *Orcid.* icon: orcid, icon_pack: ai
- *Google Scholar.* icon: google-scholar, icon_pack: ai
- *GitHub.* icon: github, icon_pack: ai
- *LinkedIn.* icon: linkedin, icon_pack: fab
- More icon options here:
	- fab: https://fontawesome.com/icons?d=gallery&s=brands
	- fas, far: https://fontawesome.com/icons?d=gallery&s=regular,solid
	- ai: https://jpswalsh.github.io/academicons/

### content/doc
If you want to reference a PDF or other document in a page (e.g., your CV, see Carolyn's `author` profile as an example), upload it here. Note that publications have a different process - see details below.

### content/event (aka Presentations)
To **add a presentation**:
1. Copy `content/event/blank` and rename to the new presentation using the format `YYYY_MM_Conference_FirstAuthorLastName`
2. Update `_index.md` with the information for the presentation.
3. Upload a logo of the conference/venue and name it `featured.jpg` (or `.png` or `.webp`). Most logos used to date are around 200px by 200px, with a few notable exceptions. You may want to play around with the size to ensure it matches the other logos when displayed. Check both the list of presentations and the individual presentation page.

### content/people
This directory (`content/people`) contains just an `index.md` file which controls the appearance (sorting and grouping) of the `People` page. To add a new lab member, don't adjust anything here - instead, see `Authors` above.

### content/project
To add a project:
1. Copy the `blank` directory under the `content/project` directory.
2. Change the name of the directory to `YYYYProjectStarted_ShortName`.
3. Add an icon with the filename `featured.png` (or `.jpg` or `.webp`)
4. Add project info to `index.md`.
5. Add the project name (i.e., `YYYYProjectStarted_ShortName`) to related presentations and publications.

If you remove/refactor a project, be sure to update presentations and publications accordingly as well.

### content/publication (aka Papers)
To **add a publication**:
1. Copy `content/publication/blank` and rename to the new publication using the format `lastnamefirstauthor-YYYY-first-three-words`
2. Update `_index.md` with the information for the publication.
3. Upload a pdf of the publication with the same name as the directory (i.e., `lastnamefirstauthor-YYYY-first-three-words.pdf`)
4. Upload a `cite.bib` file that contains the appropriate citation for the publication in question. Generate this in Zotero by right clicking on the publication name in Zotero > Export Item > Format: Better BibTeX > save file as `cite.bib` and copy to the publication directory.

## Advanced customization

### Initial website changes
The basic files you need to update in order to **switch from the template content to your custom content** are detailed in the [commits](https://github.com/cvoter/website-research-group/commits/main/) from 2025-03-15 and 2025-03-16. 

### Colors and styling
I have updated the **colors, font, and hyperlink styling** to more closely match the University of Delaware's styles. Commits that detail these changes include:
- [Commit 8e313b4](https://github.com/cvoter/website-research-group/commit/8e313b42d29fb7875d90450e6fe714448e8a8433) on 2025-03-15
- [Commit 29e7b70](https://github.com/cvoter/website-research-group/commit/29e7b705f0d198add2e503eb5f056687de948c95) on 2025-03-16

### Custom footers for author and project pages
My favorite change I have made to the template website is to **display related content** (projects, publications, presentations) in the footer of **author and project pages**. The key aspects of that functionality are detailed in:
- [Commit cef7ad9](https://github.com/cvoter/website-research-group/commit/cef7ad9c13fb1e979eac7878959eafa2f46bad09) on 2025-03-16

## Publishing to a custom domain
[The steps](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages) to using a **custom domain** for your GitHub pages website appear to be:
1. **Secure the domain**. You need to own the domain first, of course. I used to use BlueHost as my domain registrar, and also used them to host my old (Wordpress) website. But they jacked up their prices dramatically during renewals. So during the creation of this website, I transfered my domains to [Namecheap](https://www.namecheap.com/). It feels like the best registrars are always changing, so check the latest collective wisdom of the internet before picking your own registrar.
2. **Verify your domain** for GitHub pages. See the steps [here](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages) to do this for your profile. This helps make sure no other GitHub profiles can grab your domain if you e.g. delete your current website repository.
3. **Add your domain** to your website repository. See the steps [here](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site) to do this for your website repository.