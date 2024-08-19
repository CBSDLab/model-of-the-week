# Notes on preparing and maintainng "Model of the Week"

This document provides an overview of the tools and command for maintaining the model-of-the-week repository. 

## Git command for adding a model as a submodule

Models of the week are set up within their own repository, which can be under the CBSDLab organizational repository or another public repository. These are then added to the model-of-the-week repository as a submodule. This makes the respository visible within the model-of-the-week repository as a folder with a reference to a specific commit. If the model is subsequently updated with later commits, these will not be reflected in the model-of-the-week until explicitly updated. 

To add a repository to the model-of-the-week respository, open up a terminal on a local clone of the repository and execute the following command where <github repository> refers to the URL for the repository of the model:

```
git submodule add <github repository>.
```
## Git command for updating a submodule in "Model of the Week" 

As model repositories are modified, we may periodically want to pull the changes from a model into the "Model of the Week" repository. To do this via termial in the local director, update the submodule from the remote repository, commit the change and push the changes back to the main remote repository:

```
git submodule update --remote
git commit -a -m "updated submodule..."
git push
```
Remember to update any URLs to reflect the change since the updated submodule will refer to a new commit. 
