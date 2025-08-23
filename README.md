### German Learning: Definitive Guide and Notes
<p align="center">
    <img src="graphics/cover.svg" alt="drawing" width="200"/>
</p>

---

#### Contents
- A manual for learning the German language as a  Foreigner, using first principle method
- Personal learning notes from various learning courses.
- Flashcards
- Companion book to the future German learning app
---

#### Development
- Environment: VSCode and the [Tex Workshop Extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
- Formating:
```
sudo pacman -S texlive-binextra \
    perl-yaml-tiny  \
    perl-app-cpanminus \
    perl-file-homedir
# change formatter to latex-indent in plugin settings.
```
- Dependencies:
```
# gnu-free-fonts: to render hyphen with diaeresis
sudo pacman -S \
    texlive \
    inkscape \
    gnu-free-fonts

# windows fonts
<!-- yay -S ttf-ms-win10-zh_cn -->
https://wiki.archlinux.org/title/Microsoft_fonts#Extracting_fonts_from_a_Windows_ISO

```
- Build: using Tex Workshop

---

#### Rationales
- Why Latex?
    - Programmical yet flexible (elements are uniformed, deterministic)
    - Modular and reusable (custom commands)
    - Easier to maintain (e.g. changing design themes etc)
    - Printable (requires no runtime)
- Why not Latex?
    - Learning Curve
- Why not Markdown/Obsidian?
    - Lack in expressiveness (e.g. stylized table, shapes)
- Why not WYSIWYG like lyx, or MS word?
    - Not programmical (can't generate card deck from csv)
- Why not html/javsacript?
    - Tremendous waste of time reinventing the wheel 
    - Better suited for apps
    - Requires runtime

---

#### Roadmap
- from [anki plugin](https://github.com/illuminati360/gfm) to standalone app
- WYSIWYG note taking, export to latex

#### LMF Assisted Word Builder
- Rationale:
    - linguistics:《德语词汇巧学妙记》(王京平) to build a "WordNet"
    - knowledge graph
- Technical Roadmap
    - Modeling: [ontolex](https://www.w3.org/2016/05/ontolex/)-[lemon](https://lemon-model.net/)
    - Dataset: [DBnary](https://kaiko.getalp.org/) over [odenet](https://github.com/hdaSprachtechnologie/odenet)
        - open (as opposed to [GermaNet](https://uni-tuebingen.de/en/faculties/faculty-of-humanities/departments/modern-languages/department-of-linguistics/chairs/general-and-computational-linguistics/ressources/lexica/germanet/))
        - better data quality (wikitionary vs automation)
        - better modeling (ontolex over [OWL](https://www.w3.org/TR/owl2-rdf-based-semantics/))
    - RDF Server: [oxigraph](https://github.com/oxigraph/oxigraph) over [Apache Jena Fuseki]
        - newer (rust vs java, actively maintained)
        - easier setup (fuseki docker no working GUI)
    - Design and Workflow:
        - expand on ontolex-lemon to enable:
            - mnemonic hint
            - timestamp for srs
            - etc.
        - markdown as user input, e.g.:
        ```markdown
        # drucken
        ## 1
        - @hint: 
        - @derive:
            - ausdrucken: to print on
            - der Eindruck
        - @similar:
            - drücken-3: to press/squeeze, drucken只是印, drücken挤更狠
        
        # ändern
        ## 1,2
        - @hint: ander-1, 使不同就是变
        # 1
        - sich andern: to var

        ```