# 👨‍💻 Setup a development environment for Morphe

A certain development environment is suggested to allow for streamlined development on Morphe.

## 🚀 Get started

2. **Fork patches template repository**
https://github.com/morpheapp/morphe-patches-template
Read the readme notes in https://github.com/morpheapp/morphe-patches-template for additional instructions.

1. **Clone your forked patches template repository, and Desktop required to patch using the console**

    Replace `MyGitHubUserAccount` with your GitHub username.

    ```bash
    mkdir morphe
    cd morphe
   
    git clone -b dev https://github.com/MorpheApp/morphe-desktop
    git clone -b dev https://github.com/MyGitHubUserAccount/morphe-patches-template
    ```

2. **Build**

    To build patches:

    ```bash
    cd morphe-desktop
    ./gradlew build
    cd ..
   
    cd morphe-patches-template
    ./gradlew buildAndroid
    cd ..
    ```

> [!NOTE]
> If the build fails due to authentication, you may need to authenticate to GitHub Packages.
> Create a personal access tokens with the scope `read:packages` [here](https://github.com/settings/tokens/new?scopes=read:packages&description=Morphe) and add your token to ~/.gradle/gradle.properties. Create the file if it does not exist.
>
> Example `gradle.properties` file:
>
> ```properties
> gpr.user = <GitHub username>
> gpr.key = <Personal access token>
> ```


## ⌨️ Simple terminal patching with Desktop and custom patches

Copy paste the following to terminal, or add all of this to a script file:
```bash
#!/bin/sh

cd morphe-desktop
./gradlew build
cd ..

cd morphe-patches-template
rm patches/build/libs/patches*.mpp
./gradlew buildAndroid
cd ..

# replace $1 with your input apk if not using a bash script
java -Xms1024m -jar morphe-desktop/build/libs/morphe-desktop*-all.jar patch --patches morphe-patches-template/patches/build/libs/patches*.mpp --out morphe.apk $1 --install
```

Then run using: `./patch input.apk` where `input.apk` is the unmodified apk you are patching.


## ⚙️ Setting up your workspace in IntelliJ IDEA

### ⚠️ Warning: Intellij complexity ahead
If setting up Intellij in this way is to complex for your liking, then consider using the terminal approach described above.

Follow these steps to configure your development environment for the `morphe-desktop` project in IntelliJ IDEA:

1. **Open the `morphe-desktop` project**:

   - Open the `morphe-desktop` project in IntelliJ IDEA
   - Ensure you are using the correct JDK as specified in [💼 Prerequisites](0_prerequisites.md)

2. **Import projects**:

   Import the projects you cloned as modules into the `morphe-desktop` project:

   1. Open the **Project Structure** dialog by pressing **Ctrl + Alt + Shift + S**
   2. Navigate to the **Modules** section
   3. Import each additional project as a module under the `morphe-desktop` project

3. **Synchronize Gradle projects**:

   - Click on the **Sync All Gradle Projects** button in the Gradle tool window
   - Verify that all Gradle projects are imported successfully without errors

4. **Configure the Run Configuration for `morphe-desktop`**:

   1. Locate the `app.morphe.desktop.command.MainCommandKt` class in the `morphe-desktop` project
   2. Click the green **Play** button next to the `main` function. This will generate a new run configuration
   3. Edit the run configuration as follows:

      - **Program arguments**: Specify the arguments you would use to run Morphe CLI from the command line. Example:

        ```sh
        patch
        --patches morphe-patches-template\patches\build\libs\patches-<version>.mpp
        binaries\some.apk
        --install # Install the patched APK to a device connected via ADB after patching
        ```

      - **Working directory**: Set to the parent directory of the `morphe-desktop` project:

        ```sh
        $ProjectFileDir$/..
        ```

      - **Before launch**: Add a Gradle task to build `morphe-patches:patches`:

        1. Click the **+** button and select **Run Gradle Task**
        2. Choose the `morphe-patches:patches` project and add the `build` task

> [!WARNING]
> The MPP file names in `morphe-patches-template` change with each release.  
> **Ensure you update the path to the patches in the run configuration program arguments whenever you pull new commits.**

### 🥼 Working on `morphe-patcher` and `morphe-library` (Extremely optional)

1. **Import as modules**: Import `morphe-patcher` and `morphe-library` as modules in the `morphe-desktop` project

2. **Configure module dependencies**:

   - Go to **Project Structure**
   - Select the `main` module of your project
   - Under the **Dependencies** tab, remove the existing dependencies to `morphe-patcher` or `morphe-library`
   - Add new dependencies by clicking `+` > **Module Dependency**
   - Select `morphe-patcher.main` or `morphe-library.jvmMain`

6. **Set up local publication**:

   - Add **Before launch** tasks in the `morphe-desktop` run configuration
   - Use the `publishToMavenLocal` Gradle task to publish the `morphe-patcher` and `morphe-library` projects to your local Maven repository

## ✅ Verify your setup

Now that you have set up your development environment, verify that everything works as intended:

1. **Run Morphe Desktop**:

   - Run the `morphe-desktop` project with the run configuration you created
   - Confirm that the Desktop starts and executes the command you specified in the program arguments

2. **Edit the projects**:

   Make a small change in the projects and confirm that the changes are reflected, when you run the project

3. **Test debugging**:

   - Set a breakpoint in the projects
   - Run the project in debug mode and confirm that the breakpoint is hit
   - Continue and let Morphe Desktop exit

## ⚠️ Troubleshoot your development environment

- **Projects fail to build**: Ensure that you have the correct JDK version installed. Check the `JAVA_HOME` environment variable and the JDK version in IntelliJ IDEA. Make sure you are authenticated to GitHub Packages if the build fails due to authentication issues
- **Run configuration fails**: Check the program arguments and working directory in the run configuration. Ensure that the paths are correct and up to date with the latest changes in the repositories
- **Breakpoints are not hit**: Ensure that you are running the project in debug mode and that the paths are correct in the run configuration
- **Dependencies are not resolved**: Make sure, the dependencies are published to the local Maven repository
- **Changes in projects are not reflected**: Ensure, that after making changes in the projects, the `morphe-patches-template` project is built, and the run configuration is updated with the latest path to the patches file.

## 📜 Project specific documentations

To learn more about the individual projects, refer to their respective documentations:

- [Morphe Desktop](https://github.com/MorpheApp/morphe-desktop/tree/main/docs)
- [Morphe Patcher](https://github.com/MorpheApp/morphe-patcher/tree/main/docs)
