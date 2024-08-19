# Notes on preparing and maintainng "Model of the Week"

This document provides an overview of the tools and command for maintaining the model-of-the-week repository. 

## Git command for adding a model as a submodule

Models of the week are set up within their own repository, which can be under the CBSDLab organizational repository or another public repository. These are then added to the model-of-the-week repository as a submodule. This makes the respository visible within the model-of-the-week repository as a folder with a reference to a specific commit. If the model is subsequently updated with later commits, these will not be reflected in the model-of-the-week until explicitly updated. 

To add a repository to the model-of-the-week respository, open up a terminal on a local clone of the repository and execute the following command where <github repository> refers to the URL for the repository of the model:

```
git submodule add <github repository>.
```
