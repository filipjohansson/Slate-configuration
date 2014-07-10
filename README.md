#Slate configuration
Configuration file for my [Slate](https://github.com/jigish/slate) setup.

## Installation
Clone this repository to a folder of your choice and follow this guide to get going. This setup is using a "Hyper" key, we will assume you want it set to Caps Lock.

###Install PCKeyboardHack
First step is to install [PCKeyboardHack](https://pqrs.org/macosx/keyremap4macbook/pckeyboardhack.html.en) to bind the Caps Lock key to F19 (a key that doesn't even exist on most keyboards).

1. Launch `PCKeyboardHack`
2. Check the checkbox next to `Change Caps Lock`
3. Set it to keycode `80`

In order to not confuse OS X you have to disable to Caps Lock as well.

1. Open `System Preferences`
2. Go to `Keyboard`
3. Click `Modifier Keys...` button
4. Next to `Caps Lock (⇪) Key` select `No Action` (make sure you do it on every keyboard if you have more than one connected)

###Install KeyRemap4MacBook
Now you have to install [KeyRemap4MacBook](https://pqrs.org/macosx/keyremap4macbook/) in order to bind the F19 to "Hyper" key (Control + Shift + Option + Command).

1. Launch KeyRemap4MacBook
2. Go to `Misc & Uninstall`
3. Click `Open private.xml` under `Custom Setting`
4. Make sure it has the following content and save it.

````
<?xml version="1.0"?>
<root>
    <item>
        <name>Remap F19 to Hyper</name>
        <appendix>OS X doesn't have a Hyper. This maps F19 to Control + Shift + Option + Command.</appendix>

        <identifier>usercustom.f19_to_hyper</identifier>

        <autogen>
            --KeyToKey--
            KeyCode::F19,

            KeyCode::COMMAND_L,
            ModifierFlag::OPTION_L | ModifierFlag::SHIFT_L | ModifierFlag::CONTROL_L
        </autogen>
    </item>
</root>
````

###Final step
Get the latest version of [Slate](https://github.com/jigish/slate) then run this command in the terminal from the folder where you cloned the repository. This will create a symlink in the user folder that Slate can read.

`ln config.slate ~/.slate`

Open Slate and enjoy!

##How to use
This setup uses the following keyboard shortcuts.

Shortcut | What it does
---|---
⇪ + A|First trigger: Move and resize the window to the left side of the screen, Second trigger: Throw window to screen to the left
⇪ + S|First trigger: Move and resize the window to the right side of the screen, Second trigger: Throw window to screen to the right
⇪ + Z|Undo last action
⇪ + Space|First trigger: Move and resize the window to screen center, Second trigger: Move and resize the window to full screen
⇪ + X|Hide the window
⇪ + G|Show the grid
⇪ + 1|Switch to "Mail"
⇪ + 2|Switch to "Google Chrome"
⇪ + 3|Switch to "Skype"
⇪ + 4|Switch to "Messages"
⇪ + Q|Switch to "Sublime Text"
⇪ + W|Switch to "Google Chrome" (Still waiting for a good way to switch to Canary)
⇪ + R|Switch to "iTerm"
⇪ + E|Switch to "SourceTree"
⇪ + Return|Relaunch Slate

##Resources and read more
A [blog post by Tristan Hume](http://thume.ca/howto/2012/11/19/using-slate/) was the main reason I started using Slate and the Caps Lock Hack was taken from a [blog post by Tenshu](http://www.tenshu.net/2012/11/using-caps-lock-as-new-modifier-key-in.html).

I'm always interested in enhancing my workflow so feel free to fork and make pull requests!
