I use [zotero.org](https://zotero.org) for managing a large collection of scientific papers, most with PDFs, in two areas:

* Computational Cognitive Neuroscience: [CCNLab](https://www.zotero.org/groups/340666/ccnlab)
* Mechanistic models of physics: [MechPhys](https://www.zotero.org/groups/2525742/mechphys)

Any responsible individual with interest in these areas may ask to join. It is useful if you send me an email along with your request on the zotero website, if I don't otherwise know you: `oreilly@ucdavis.edu`

If you want to add papers to these collections, then you _MUST_ configure zotero as below, to ensure consistency in the database. Anyone who adds papers without the proper configuration could be removed from the groups.

The key goal of the configuration is to give every paper a consistent citation key, based on the first 3 author's last names, and a 2 year date, e.g., `MarkovMiseryFalchierEtAl11`. We also rename the PDF file with this same name, so it is easy to identify when used outside of zotero.

## Configuring Zotero

* You _MUST_ update / download zotero version **8** (or higher), which has significant new features including a new database structure that includes `Citation key` (finally!).

* Install the following essential `Plugin`s
    + [Better BibTeX](https://retorque.re/zotero-better-bibtex/) (see Installation instructions on that website).
    + [Attanger](https://github.com/MuiseDestiny/zotero-attanger): click on the latest release on the right under `Releases`, then download the `zotero-attanger.xpi` file, and follow same instructions as for Better BibTeX.
    
In the `Settings` / `Preferences`:

The default for most settings should be fine. Except these key ones:

### General

* `Automatically rename files`, click on `Custom Format`, and enter `{{ citationKey }}` for the template. Attanger uses this setting, but is still needed for the menu command to rename on demand.

### Better BibTeX

* `Citation key formula`: `authors(n=3,etal=EtAl)+shortyear`

* `Fields to omit from export`: `abstract, file`

* `Miscellaneous` / `Sort TeX/CSL output`: `citation key`

* `Enable caching`: yes

## Updating to zotero 8

If you have an existing zotero 7 installation with BetterBibTeX installed, you may get a prompt about moving the citation keys over to the new `Citation key` field -- this has already been done so it should not be necessary, but it also should not matter to have it do this again, or not. This prompt recurring probably means that someone has accessed the database without updating to zotero 8.

## Usage notes

1. **Be sure to check for an existing entry before adding**, and if you accidentally add a duplicate (it will end with `a` in the citekey as a clue) please delete it or merge it using `Duplicate items` section.  Zotero docs: https://www.zotero.org/support/duplicate_detection

2. To organize the list of citations by most recently added, which is very handy for checking recent updates,  click on the tiny button on the far right of the list header to select the fields to show, and select Date Added and `Citation key` (e.g., use Title, Creator, Date Added, `Citation key` as the full set). Then, click on Date Added to sort by that, so you can see the newest ones at the top.

