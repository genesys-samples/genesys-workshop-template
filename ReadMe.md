# Welcome to the Genesys workshops template repository

The purpose of this repository is to provide Genesys partners with guidance on how to create a workshop.

## Repository Structure
```
genesys-workshop-template
├───.github
│   └───workflows
├───archetypes
├───content
│   ├───010-Introduction
│   ├───020-Getting-Started
│   └───090-Conclution
├───layouts
│   └───partials
├───resources
│   └───_gen
│       ├───assets
│       └───images
├───static
│   ├───css
│   └───images
└───themes
    └───hugo-theme-learn
 ```
## How to Contribute 

Once you have created your own fork, you can begin contributing to the "Content" folder seen in the repository structure above. You can think of the folders within "Content" as modules. For example, if you wanted to add a module about "Setting Up", you would add a folder to the "Content folder" and title it "030-Setting Up". You would then add your information to that module. The number before the title signifies the order of that module. So "030-Setting Up" would come after "020-Getting Started" and before "090-Conclution". 


![Content](https://user-images.githubusercontent.com/101136030/175966338-74f85fb3-5155-4254-86fd-a7f7a00b308f.jpg)

You can then organize your content within that folder by adding markdown files. To add a markdown file, right click the folder you want this file to appear in and select "New File". Give the submodule a title that reflects its numerical order followed by ".md". For example, if you wanted the module "020-Getting Started" to have 2 "submodules", you would title the first one  "10_first.md" and the second one "20_second.md". (Note: files have to end in ".md" for the system to recognize it as a markdown file).
![Submodules](https://user-images.githubusercontent.com/101136030/175968183-f93d1cab-7b62-42ce-a023-a283d3e32b13.jpg)


To add information to your module's landing page, you can edit the "index.md" file. For example, if I wanted my "030-Setting Up" landing page to have an objective, welcome, etc, I would add that to the "index.md" file.

![Index](https://user-images.githubusercontent.com/101136030/175969626-6044c4ac-f1d8-481b-a0d0-f119bdd6009b.jpg)


Images can be added to the "Images" subfolder under the "Static" folder. Once the images are uploaded to this folder, you can begin referencing them using markdown language.


![Screenshot_062722_095857_AM](https://user-images.githubusercontent.com/101136030/175971521-eff9951d-b1b3-4ece-bc66-97baaf27aa1e.jpg)
