---
icon: material/laptop
---

# Developing RevoltUltimate

Here is how to compile RevoltUltimate

---

## Prerequisites

To compile and modify RevoltUltimate, you will need to set up your Windows development environment with the following tools:

1. **[Visual Studio 2022](https://visualstudio.microsoft.com/)** (Community, Professional, or Enterprise)
   * During installation, make sure you select the **.NET desktop development** workload (this installs the necessary tools for Windows Presentation Foundation / WPF).
2. **[Git](https://git-scm.com/downloads)** (for cloning the repository and downloading submodules).
3. **[Rust Toolchain](https://rustup.rs/)** (Cargo).
   * This is explicitly required to compile the `cometOffline` network interceptor module.

---

## 1. Cloning the Repository

RevoltUltimate relies on a powerful Git Submodule for its offline networking component. **You must clone the repository recursively** to ensure you pull the Rust code too!

Open your command prompt or terminal and run:

```bash
git clone --recursive https://github.com/ricky074game/RevoltUltimate.git
```

*(If you already cloned it normally without the recursive flag, you can fix it by opening a terminal inside the folder and running `git submodule update --init --recursive`)*.

---

## 2. Building the Project

RevoltUltimate consists of two main parts: the C# Interface/API built via Visual Studio, and the Rust Comet server submodule. **You must compile the Rust module first.**

### Step A: Compile the Rust Submodule (`cometOffline`)

1. Open a terminal or command prompt.
2. Navigate into the `cometOffline` directory inside your cloned folder:

   ```bash
   cd RevoltUltimate\cometOffline
   ```

3. Build the highly-optimized release version using Cargo:

   ```bash
   cargo build --release
   ```

4. This command will output the compiled `comet.exe` binary, which the main C# application will look for when running GOG offline games.

### Step B: Compile the C# Projects

1. Go back to the main `RevoltUltimate` folder and double-click **`RevoltUltimate.sln`** to open it in **Visual Studio 2022**.
2. Look at the top toolbar in Visual Studio and make sure your build configuration is set to **Debug** or **Release** (right next to the green play button).
3. Right-click on **`RevoltUltimate.sln`** in the *Solution Explorer* on the right side of the screen, and click **Restore NuGet Packages**. This downloads all the required open-source libraries.
4. If it isn't bolded already, right-click **`RevoltUltimate.Desktop`** in the Solution Explorer and select **Set as Startup Project**.
5. Press **F5** on your keyboard (or click the green **Start** button).

---

## 3. How to Contribute

We actively welcome Pull Requests from the community! If you want to fix a bug, improve the UI, or add a brand-new feature:

1. **Fork** the main [RevoltUltimate repository](https://github.com/ricky074game/RevoltUltimate) on GitHub using the web interface.
2. **Clone** your new personal fork to your PC recursively (as explained in step 1).
3. **Create a new branch** for your feature before writing code:

   ```bash
   git checkout -b feature/my-cool-feature
   ```

4. Make your desired code changes in Visual Studio or your favorite editor.
5. **Commit your changes** with a clear message:

   ```bash
   git commit -am "Added my cool new feature"
   ```

6. **Push to your branch** on your GitHub fork:

   ```bash
   git push origin feature/my-cool-feature
   ```

7. Go back to the main repository on GitHub.com and click **Compare & pull request** to send your code to us for review!
