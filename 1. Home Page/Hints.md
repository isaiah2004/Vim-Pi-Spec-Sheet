## Slight hint.

Initialize a git project and install textual via pip to implement

## Moderate Hint 

Install textual and textual dev tools via pip.

Make a base Program that shows an empty app

Add main screen with App Name

## Giveaway Hint 

create and activate python virtual env:

```sh
python -m  virtualenv .venv
#windows shell
.\.venv\Scripts\Activate.ps1
#linux and mac
source ./.venv/bin/activate
```
install textual and tools using pip 

```sh
pip install textual textual-dev
```
store requirements.txt using
```sh
pip freeze > requirements.txt
```


initialize the base code by importing and declaring a class in this format:
```py
from textual.app import App

class TextualApp(App):
	pass


if __name__ == "__main__":
    app = TextualApp()
    app.run()
```

Initialize the home page 

```py 
from textual.app import App, ComposeResult
from textual.widgets import Header, Footer, Static


class TextualApp(App):
    """A Textual app to manage stopwatches."""

    BINDINGS = [("d", "toggle_dark", "Toggle dark mode")]

    def compose(self) -> ComposeResult:
        """Create child widgets for the app."""
        yield Header()
		yeild Static("Vim-pi")
        yield Footer()

    def action_toggle_dark(self) -> None:
        """An action to toggle dark mode."""
        self.dark = not self.dark


if __name__ == "__main__":
    app = TextualApp()
    app.run()
```

Add the Home screen and File explorer screen logic
use the screens module

```py
from textual.app import App, ComposeResult
from textual.screen import Screen
from textual.widgets import Static

ERROR_TEXT = """
An error has occurred. To continue:

Press Enter to return to Windows, or

Press CTRL+ALT+DEL to restart your computer. If you do this,
you will lose any unsaved information in all open applications.

Error: 0E : 016F : BFF9B3D4
"""


class BSOD(Screen):
    BINDINGS = [("escape", "app.pop_screen", "Pop screen")]

    def compose(self) -> ComposeResult:
        yield Static(" Windows ", id="title")
        yield Static(ERROR_TEXT)
        yield Static("Press any key to continue [blink]_[/]", id="any-key")


class BSODApp(App):
    CSS_PATH = "screen01.tcss"
    SCREENS = {"bsod": BSOD}
    BINDINGS = [("b", "push_screen('bsod')", "BSOD")]


if __name__ == "__main__":
    app = BSODApp()
    app.run()
```

