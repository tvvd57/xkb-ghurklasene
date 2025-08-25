*warning: your system must use X11 for keyboard related functions, in order for the following tutorial to work. This includes most KDE installations*

First of all download the ``ghurklasene`` file and then move it to ``/usr/share/X11/xkb/symbols>``. You can do so using the following script
```zsh
sudo mv <where you downloaded the file>/ghurklasene /usr/share/X11/xkb/symbols
```

now we'll need to edit  ``evdev.xml``, I advice you to not mess this up, as this would probably make you unable to type.
for this, we'll use nano, any text editor would work.
```zsh
sudo nano /usr/share/X11/xkb/rules/evdev.xml
```

before a "<layout>" line, past the following:
```xml
<layout>
      <configItem>
        <name>ghurklasene</name>
        <description>Ghurklasene</description>
      </configItem>
      <variantList>
        <variant>
          <configItem>
            <name>basic</name>
            <description>Ghurklasene (Basic)</description>
          </configItem>
        </variant>
      </variantList>
    </layout>
```

save and exit


now we'll modify ``evdev.lst``. Open it, then after the ``! layout`` line, add:
```lst
  ghurklasene Ghurklasene
```

And now after the ``! variant`` line, add:
```lst
  basic ghurklasene: Ghurklasene (Basic)
```

Don't forget to save, then congrats! just a mere system reboot then your keyboard is ready to use
