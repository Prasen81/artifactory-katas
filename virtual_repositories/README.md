# Virtual repositories

You want to have one endpoint for all developers to get their artifacts regardless of maturity or if they are internal or external.
At the same time, you also want all published artifacts to go into the repository with lowest maturity.

After executing the setup script, you will see four local repositories, each with different maturity denoted:

* USERNAME-gradle-sandbox-local
* USERNAME-gradle-dev-local
* USERNAME-gradle-v3-local
* USERNAME-gradle-release-local

What we need now is a remote repository and a virtual spanning them all, making sure that all artifacts published to the virtual goes in the sandbox repository.

## Task

* If you haven't created a remote repository yet, do that (head over to [Gradle dependency management](./gradle_dependency_management/README.md) for detailed instructions).
* Create a Gradle typed virtual repository that spans all four local and the remote repository
* Set Default Deployment Repository to your sandbox repository to make you able to upload artifacts to the repository.
* Upload `duck.jpg` and `fox.jpg` through the UI to the virutal repository you just created, following the repository layout.
* Add the new repository URL for resolving dependencies to your `build.gradle` file.
* Add both images to your gradle dependencies in your `build.gradle`.

    **Hint:** If you visit your artifact in the Gradle UI, have a look at the `General` tab, under `Dependency Declaration`. Artifactory has already made the dependency declaration for you, ready to paste into your build script.
* Run `gradle dependencies --refresh-dependencies` and check that your artifact resolves.
