# Getting Your Feet Wet

## A Simple Example

To get an idea of how the modules from the `GTK::V3` package work, a simple example is shown where a window is opened. When the window manager button ![wm button](Images/manager-quit-button.png) is clicked, the application will stop and the GUI will disappear.

| Example Window |
|-----|
| ![example window](Images/simple-example.png) |

~~~~ {.number-lines .codeblock}
use v6;

use GTK::V3::Gtk::GtkMain;
use GTK::V3::Gtk::GtkWindow;

my GTK::V3::Gtk::GtkMain $m .= new;

class AppSignalHandlers {
  method exit-program ( ) {
    $m.gtk-main-quit;
  }
}

my GTK::V3::Gtk::GtkWindow $top-window .= new(:title<Example>);

my AppSignalHandlers $ash .= new;
$top-window.register-signal( $ash, 'exit-program', 'destroy');

$top-window.show-all;
$m.gtk-main;
~~~~

Lets explain some of the code displayed above. To start with, every Perl6 program starts with `use v6` with variants like `use v6.c` [line 1]. Then we need to load the modules used in this program. These are `GTK::V3::Gtk::GtkMain` and `GTK::V3::Gtk::GtkWindow` [3,4]. They will load class definitions having the same names.

Next, we initialize a `GTK::V3::Gtk::GtkMain` object `$m` which will be used later on [6].

Then we will setup a class to handle signals. These signals are registered after all widgets are setup and laid out [8-12]. There is only one method defined in that class to stop the program. Our first GTK method is used here, `gtk-main-quit` from the `GTK::V3::Gtk::GtkMain` class.

Now we can start creating the widgets. There is only one widget `GTK::V3::Gtk::GtkWindow` and initialized as a window with its title set to 'Example' [14].

Initialize the handler class and register signals. We use the `destroy` signal to call the `exit-program` method in the handler object `$ash` [16,17].

Then show the window and everything in it [19] and start the main loop [20].

To run the program, save the code in a file called `simple-example.pl6` and type the following.
```
perl6 simple-example.pl6 <Enter>
```

## Simple Example With A Button
