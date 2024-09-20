# Sub-task 2 : Implement a File explore and editor with saving Feature

#### Objective:

Set up a textual Screen with a **File explorer** and **code editor** component that allows users to edit and write code.

---
#### Requirements:
1. Add a shortcut to open and close the file explorer Screen. use `ctrl+f` as the shortcut and use the action system in textual and name it : `action_toggle_file_explorer()`
2. Add a File Explorer screen and make a panel that occupies 1/3~ of the available width. Name the File explorer widget : `FileExplorer()`
3. Add a File Explorer Event that emits a message every time file is selected. Name the event: `TextViewerUpdated()`
4. Add A save shortcut using the action_ system from the Textual. Name it:`action_save_current_file()`
5. Add a Close file shortcut `ctrl+w` implement using `action_close_current_file()`

---
#### Instructions

1. use the actions system in textual.
2. Use the events and messages system to create copy and paste. 
3. Make sure the Textual system is also aware of the previously copied text.
4. Ensure that the functions can handle replacement paste.


