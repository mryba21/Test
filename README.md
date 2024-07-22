# Food Log Application
The Food Log Application is a TkInter-based application designed to help users log and track their daily food intake. This repository contains the source code for the application, which is primarily implemented in Python using the TkInter library for the GUI.

## Table of Contents

- [API Key Setup](#api-key-setup)
- [Installation](#installation)
- [Usage](#usage)
- [Main Application](#main-application)
- [Functions and Methods](#functions-and-methods)
- [Contributing](#contributing)
- [License](#license)

## API Key Setup

To use the Edamam food database API, you need to obtain an API key and application ID:

1. Sign up for an API key and application ID at the [Edamam Developer Portal](https://developer.edamam.com/).
2. Create a file named `api_keys.py` in the project directory and add your API key and application ID in the following format:
> [!IMPORTANT]
> An API key file is required to return results from the application.

 ```python
  EDAMAM_APP_ID = 'your_app_id_here'
  EDAMAM_APP_KEY = 'your_api_key_here'
``` 
4. Save the file.

## Installation

To install and run the Food Log Application, follow these steps:

1. Clone the repository:
 ```bash
    git clone https://github.com/jocelyngilbertson/foodlogapp.git
 ``` 
2. Navigate to the project directory:
 ```bash
    cd foodlogapp
 ``` 
3. (Optional) Create and activate a virtual environment:
 ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
``` 
4. Install the required dependencies using the file ```Package Installation.py``` or 
 ```python
  import subprocess
  import sys
   
  def install(package):
      subprocess.check_call([sys.executable, "-m", "pip", "install", package])
   
  # Install packages
  install("opencv-python")
  install("pyzbar")
  install("requests")
  install ("ttkbootstrap")
``` 
## Usage

To run the application, execute the following command:

```bash
python run_TkInter.py
``` 

## Main Application

The main application logic is contained within the `run_TkInter.py` file. Below is an overview of its structure and key components:

### `run_TkInter.py`

This is the entry point of the application. It initializes the TkInter GUI and handles user interactions. The key components include:

-   **Initialization**: Sets up the main window and its properties.
-   **Widgets**: Defines and places widgets such as labels, entry fields, buttons, and listboxes.
-   **Event Handling**: Contains functions to handle events like button clicks and listbox selections.
-   **Data Management**: Includes functions to manage food log entries, such as adding, editing, and deleting entries.

```python
# Example snippet from run_TkInter.py
import tkinter as tk
from tkinter import messagebox

def main():
    root = tk.Tk()
    app = FoodLogApp(root)
    root.mainloop()

if __name__ == "__main__":
    main()
``` 

## Functions and Methods

Here's a detailed list of the key functions and methods in `run_TkInter.py`:

### Initialization and Setup

-   `__init__(self, master)`: Initializes the main application window and its widgets.
    -   **UI Elements**: Sets up the main window with input fields for food name, calories, and date, as well as buttons for adding, editing, and deleting entries, and a listbox for displaying the food log.
        

### Data Management

-   `add_food_entry(self)`: Adds a new food entry to the log.
    
    -   **Parameters**: None
    -   **Returns**: None
    -   **Description**: Retrieves the input from the entry fields and appends it to the food log.
    -   **UI Interaction**: When the user fills in the food details and clicks the "Add" button.
        
-   `edit_food_entry(self)`: Edits an existing food entry.
    
    -   **Parameters**: None
    -   **Returns**: None
    -   **Description**: Modifies the selected food entry based on the user's input in the entry fields.
    -   **UI Interaction**: When the user selects an entry from the listbox, edits the details, and clicks the "Edit" button.
        
-   `delete_food_entry(self)`: Deletes a selected food entry.
    
    -   **Parameters**: None
    -   **Returns**: None
    -   **Description**: Removes the selected entry from the food log.
    -   **UI Interaction**: When the user selects an entry from the listbox and clicks the "Delete" button.
        
-   `save_to_file(self)`: Saves the food log to a file.
    
    -   **Parameters**: None
    -   **Returns**: None
    -   **Description**: Writes the current food log to a specified file for persistent storage.
    -   **UI Interaction**: When the user clicks the "Save" button.
            
-   `load_from_file(self)`: Loads the food log from a file.
    
    -   **Parameters**: None
    -   **Returns**: None
    -   **Description**: Reads a previously saved food log from a specified file.
    -   **UI Interaction**: When the user clicks the "Load" button.        

### Event Handling

-   `on_select(self, event)`: Handles the selection of an entry in the listbox.
    -   **Parameters**: `event` (Tkinter event object)
    -   **Returns**: None
    -   **Description**: Populates the entry fields with the selected food log entry for viewing or editing.
    -   **UI Interaction**: When the user clicks on an entry in the listbox.        

### Utility Functions

-   `clear_fields(self)`: Clears all the input fields.
    
    -   **Parameters**: None
    -   **Returns**: None
    -   **Description**: Resets the entry fields to their default state.
    -   **UI Interaction**: When the user clicks the "Clear" button.
        
-   `update_listbox(self)`: Updates the listbox with the current food log entries.
    
    -   **Parameters**: None
    -   **Returns**: None
    -   **Description**: Refreshes the listbox to reflect the current state of the food log.
    -   **UI Interaction**: Automatically updates after add, edit, or delete operations.
        

## Contributing

Contributions are welcome! To contribute to the project, follow these steps:

1.  Fork the repository.
2.  Create a new branch:
    
```bash
    `git checkout -b feature-branch`
```
    
3.  Make your changes.
4.  Commit your changes:
    
```bash
    `git commit -m "Description of your changes"`
```
    
5.  Push to the branch:
    
```bash
    `git push origin feature-branch`
```
    
6.  Create a pull request.

Please ensure your code follows the project's coding standards and includes appropriate tests.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
