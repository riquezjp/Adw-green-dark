# Adw-green-dark
A 'quick fix' for Manjaro Green accents in Gnome 42 (& 43)

For anyone who cant wait, here is an easy way to get green accents back (mostly).
This is a home hack. It wont break anything & you can easily just remove the files.

THIS IS FOR DARK MODE USERS, This version is modded from `/usr/share/themes/adw-gtk3-dark`
if you use light mode you'll need to engineer your own version from `/usr/share/themes/adw-gtk3` I will document the process below.

This mod will give you manjaro green accents in nautilus, system settings & shell. As well as some gtk3 & gtk4 apps - it just covers the basics so far.

# Step 0
You will need Gnome-Tweaks installed & enable the extension user-themes.

# Step 1
Copy the file provided `gtk.css` to `~Home/.config/gtk-4.0/gtk.css`

Immediately your gtk4 apps like Settings, Calendar, Calc will have green accents.

It may be wise to rename this file to something else when offical support is ready.

**If you use Manjaro Gnome 43** you can use the app Gradience to set your accent colour to #16a085, if you do that then you dont need my gtk.css file & can skip this step. I reccomend using gradience.

# Step 2 
COPY the folder provided `Adw-Green` to `~Home/.themes/Adw-Green`


# Step 3
- Ensure the extension user-themes is enabled.
- Open Gnome-tweaks, Appearance > change Legacy Apps to `Adw-green`
- Change Shell to `Adw-green`

Close any nautilus (Files) windows you might have open & run `nautilus -q` in terminal. Then open any folder & you should see green accents.

DONE.

Note: Gnome43 green accents in the powermenu is not yet done (ie: wifi, bluetooth, nightlight buttons)
--------------------------------------------

Process:

- Create ~Home/.config/gtk-4.0/gtk.css
- COPY the folder /usr/share/themes/adw-gtk3-dark into ~Home/.themes
- RENAME to "Adw-green"
- Open "Adw-green" & edit 'index.theme' & edit the values: Name=Adw-green, GtkTheme=Adw-green
- Edit the file  ~Home/.themes/Adw-green/gtk-3.0/gtk-dark.css
- Insert a new line after green_5 to define a new green: @define-color green_6 #16a085;
- Run a Find & Replace. Find #3584e4 & replace with @green_6
- correct blue_3 back to #3584e4
- Create ~Home/.themes/Adw-green/gnome-shell/gnome-shell.css & include specific rules to overide default.

