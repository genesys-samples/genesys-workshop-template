# Welcome to the Genesys workshops template repository

The purpose of this repository is to provide Genesys partners with examples of what these workshops should look like

## Repository Structure

genesys/genesys-workshop-template <br>
├── .github <br>
│   └── workflows <br>
│       ├── gh-pages.md <br>
├── archetypes <br>
│   ├── default.md <br>
├── content (all content for workshop will be entered here. Add new chapters as needed) <br>
│   ├── 010-Introduction <br>
│   │   ├── index.md (homepage for the chapter) <Br>
│   └── 020-Getting Started <br>
│   │   ├── 10_first.md <br>
│   │   └── 20_second.md <br>
│   │   ├── index.md (homepage for the chapter) <br>
    └── 090-Conclution (misspelled purposely) <br>
│   │   ├── index.md (conclusion for the entire workshop) <br>
    └── index.md (Welcome page for the whole workshop) <br>
├── layouts <br>
│   ├── partial <br>
│   │   ├── favicon.html <br>
│   │   └── logo.html <br>
│   │   └── menu-footer.html <br>
├── static <br>
│   ├── css <br>
│   │   ├── .theme.mine.css <br>
│   ├── images <br>
│   │   ├── (images for workshop will be uploaded here) <br>
│   ├── imports <br>
│   │   ├── (downloadable documents, files, etc will be uploaded here) <br>
├── themes <br>
│   ├──hugo-theme-learn <br>
│ 

## How to Contribute 

We recommend commit and pull request messages to be clear, concise, and self-explanatory. Please specify related issues when possible

We recommend these resources to get started with Github:

- [Create a free acount](https://github.com/)
- [How to fork a repo](https://docs.github.com/en/get-started/quickstart/fork-a-repo)
- [How to create a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)

Once you have created your own fork, you can begin contributing to the "content" folder seen in the repository structure above. You can think of the folders within "Content" as modules. For example, if you wanted to add a module about "Setting Up", you would add a folder to the "Content folder" and title it "030-Setting Up". You would then add your information to that module. The number before the title signifies the order of that module. So "030-Setting Up" would come after "020-Getting Started" and before "090-Conclution". 

You can then organize your content within that folder by adding markdown files. For example, the module "020-Getting Started" has 2 "submodules": 10_first.md and 20_second.md. 

To add information to your module's landing page, you can edit the "index.md" file. For example, if I wanted my "030-Setting Up" landing page to have an objective, welcome, etc, I would add that to the "index.md" file.

Images can be added to the "Images" subfolder under the "Static" folder. Once the images are uploaded to this folder, you can begin referencing them using markdown language: ![title](Images/example.png)
