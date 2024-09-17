## Slight hint.
Implement a new screen and add a Binding


## Moderate Hint.
You can implement a new screen like:
```py
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
    
```
Add binding and register new screen in App class:
```py
class VimPi(App):
    CSS_PATH ='layout.tcss'
    # Add a binding for the screen switching
    BINDINGS=[
        ('ctrl+f', 'toggle_file_explorer()','File Explorer')
    ]
    def on_mount(self) -> None:
        #register home screen
        self.install_screen(Home(name='Home'), name="Home")
        # push home screen
        self.push_screen('Home')

```

## Giveaway Hint.

Implement the screen as
```py

```