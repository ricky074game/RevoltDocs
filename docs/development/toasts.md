---
icon: material/bell
---

# Creating Custom Toasts

RevoltUltimate features a modular notification system that allows developers to create and share their own custom achievement popups (often called "Toasts"). Whether you want a PlayStation-style popup, a classic Steam notification, or something completely unique, you can build it!

This guide will comprehensively teach you how to write your own custom toast module, read data from the system, and properly submit it to be featured in the official repository.

---

## 1. Technical Requirements & Setup

A custom toast in RevoltUltimate is simply a compiled **WPF Class Library (`.dll`)** paired with a `manifest.json` file. 

To develop one, you should:
1. Create a new **Class Library** (.NET 8.0 or applicable version) project. (C# is standard, but you can use F#, VB.NET, or any .NET language).
2. Add a reference to the **`RevoltUltimate.API.dll`** (found in your RevoltUltimate build directory). This library contains the base interfaces and objects you need.
3. *(Optional)* Build your custom UI. While most people use standard XAML (Animations, Grids, etc.), you are completely free to build the UI purely in code, use WinForms, or run any custom logic as long as it executes when the function is called!

---

## 2. Implementing the Code

The core of a custom toast revolves around a single interface: `IAchievementNotifier`. Your main Window or Class must inherit from this and implement the `ShowAchievement()` method.

Here is a simplified example of how it looks in code:

```cs
using RevoltUltimate.API.Contracts;
using RevoltUltimate.API.Objects;
using System.Windows;

namespace MyCustomToast
{
    public partial class CustomToastWindow : Window, IAchievementNotifier
    {
        public CustomToastWindow()
        {
            InitializeComponent();
        }

        // This function is fired by RevoltUltimate whenever an achievement pops
        public void ShowAchievement(Achievement achievement)
        {
            // You must handle queueing and showing the UI yourself!
            // Example:
            Dispatcher.Invoke(() => 
            {
                var popup = new CustomToastWindow();
                popup.TitleText.Text = achievement.name;
                popup.DescText.Text = achievement.description;
                popup.Show();
            });
        }
    }
}
```

### The `Achievement` Object ("Get Functions")

When `ShowAchievement(Achievement achievement)` is called, it passes an `Achievement` object containing everything you need to populate your UI. You can access its properties using standard C# getter syntax:

* `achievement.name` (string) - The localized title of the achievement.
* `achievement.description` (string) - The explanation of how to unlock it.
* `achievement.imageUrl` (string) - The direct URL or local path to the achievement icon. You can bind this directly to a WPF `Image.Source`!
* `achievement.xp` (int) - The Gamerscore/XP value. If a platform doesn't have an XP system (like Steam), RevoltUltimate dynamically calculates this based on global rarity!
* `achievement.hidden` (bool) - Whether the achievement is a secret.
* `achievement.getglobalpercentage` (float) - The percentage of global players who have unlocked this. Useful for generating "Rare Achievement" diamonds.

!!! warning "Note"
    It is **highly recommended** that you implement a Queue system in your class so that if 5 achievements pop at once, they wait their turn instead of stacking on top of each other. Look at the `RevoltUltimate.Notification` default Xbox toast source code for a great example of queueing! RevoltUltimate will NOT do it for you

---

## 3. Creating the Manifest

For RevoltUltimate to recognize your `.dll` as a valid extension, you must include a `manifest.json` file in the same folder as your compiled DLL.

```json
{
  "Id": "my-custom-toast",
  "Name": "My Custom Notification",
  "Version": "1.0.0",
  "Author": {
    "Name": "Your Name",
    "Url": "https://github.com/YourUsername"
  },
  "Description": "A beautiful new popup style.",
  "PreviewImage": "preview.png",
  "Entry": "MyCustomToast.dll",
  "Links": [ "https://yourwebsite.com" ],
  "Tags": [ "custom", "dark-mode" ]
}
```
* **`Entry`**: This must exactly match the filename of your compiled DLL.
* **`PreviewImage`**: Include an image (e.g., `preview.png`) in the folder so users can see what it looks like before equipping it.

---

## 4. Submitting Your Toast

Once you have finished your beautiful new toast, you probably want to share it with the world! **However, you DO NOT submit custom toasts via Pull Requests/Commits to the main repository.**

Instead, you must open an **ISSUE** on GitHub proposing your new layout.

### The Golden Rule for Toast Submission

!!! failure "It MUST be Open Source:"
    For your Issue to be approved and your toast featured, it must strictly meet this requirement: You cannot submit a closed-source `.dll`. Your issue must include a link to your own public GitHub repository containing the full source code (XAML, CS, resources) for transparency and security.

I will implement it to the site and get everything working for others to download! Thank you for your contribution!
