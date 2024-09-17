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
class FileExplorerAndEditorScreen(Screen):
    BINDINGS = [
        .....
        ("ctrl+s", "save_current_file()", "Save File"),
        .....
    ]
    def __init__(self,....):
        .....
    # The composition of the Editing screen
    def compose(self) -> ComposeResult:
        ....
        with Horizontal():
            with VerticalScroll(id="left-pane"):
                yield FileExplorer(path=self.CURRENT_DIR,id='FileExplorerPanel')
            with Container(id="right-pane"):
                TextViewerObject = TextViewer(id="editor", disabled=True).code_editor(id="editor")
                TextViewerObject.load_text("Open file to edit")
                yield TextViewerObject
```

You can implement the save file as something like:
```py
def action_save_current_file(self):

        try:

            file_path = self.query_one(FileExplorer).SelectedFile

            if file_path:

                data = self.query_one("#editor", TextViewer).text

                if os.path.isfile(file_path):

                    # File exists, write data to the file

                    with open(file_path, "w") as f:

                        f.write(data)

                    self.isFileOpen=True

                    self.notify("File Saved Successfully.")
```