# open-with-VSCode
Add option to open folder/file with VS Code [Win]

1. Get VSCode path.
    - Search for `Visual Studio Code` in the windows search box.
        <br>
        ![step1](/img/step1.png "Search 'Visual Studio Code'")
        <br><br>
    - Right click on it, then click on **Open file location**.
        <br>
        ![step2](/img/step2.png "Open file location")
        <br><br>
    - It should open a window like this
        <br>
        ![step3](/img/step3.png)
        <br><br>
    - Right click on **Visual Studio Code**, then click on **Properties**.
        <br>
        ![step4](/img/step4.png "Properties")
        <br><br>
    - Now copy all the text inside the **Target:** field, this will be our `path`.
        <br>
        ![step5](/img/step5.png "Copy Target Path")
        <br><br>

1. Create a `.txt` file.

1. Edit `.txt` file content.
    - First, copy and paste the code below in the `.txt` file
        ```reg
        Windows Registry Editor Version 5.00

        [HKEY_CLASSES_ROOT\*\shell\Open with VS Code]
        @="Edit with VS Code"
        "Icon"="\path, 0"

        [HKEY_CLASSES_ROOT\*\shell\Open with VS Code\command]
        @="\path \"%1\""

        [HKEY_CLASSES_ROOT\Directory\shell\vscode]
        @="Open folder with VS Code"
        "Icon"="\path, 0"

        [HKEY_CLASSES_ROOT\Directory\shell\vscode\command]
        @="\path \"%1\""

        [HKEY_CLASSES_ROOT\Directory\Background\shell\vscode]
        @="Open folder with VS Code"
        "Icon"="\path, 0"
            
        [HKEY_CLASSES_ROOT\Directory\Background\shell\vscode\command]
        @="\path \"%V\""
        ```
    
    - Now replace `path` with the text you got from target propertie.
        > Mine version looks like this:
        > ```reg
        >Windows Registry Editor Version 5.00
        >
        >[HKEY_CLASSES_ROOT\*\shell\Open with VS Code]
        >@="Edit with VS Code"
        >"Icon"="\"C:\Users\User\AppData\Local\Programs\Microsoft VS Code\Code.exe", 0"
        >
        >[HKEY_CLASSES_ROOT\*\shell\Open with VS Code\command]
        >@="\"C:\Users\User\AppData\Local\Programs\Microsoft VS Code\Code.exe" \"%1\""
        >
        >[HKEY_CLASSES_ROOT\Directory\shell\vscode]
        >@="Open folder with VS Code"
        >"Icon"="\"C:\Users\User\AppData\Local\Programs\Microsoft VS Code\Code.exe", 0"
        >
        >[HKEY_CLASSES_ROOT\Directory\shell\vscode\command]
        >@="\"C:\Users\User\AppData\Local\Programs\Microsoft VS Code\Code.exe" \"%1\""
        >
        >[HKEY_CLASSES_ROOT\Directory\Background\shell\vscode]
        >@="Open folder with VS Code"
        >"Icon"="\"C:\Users\User\AppData\Local\Programs\Microsoft VS Code\Code.exe", 0"
        >
        >[HKEY_CLASSES_ROOT\Directory\Background\shell\vscode\command]
        >@="\"C:\Users\User\AppData\Local\Programs\Microsoft VS Code\Code.exe" \"%V\""

1. Save file as `.reg`.

1. Execute `.reg` file.
    - It should pop up 2 warnings.
        <br>
        ![warning1](/img/warning1.png "Press 'Yes'")
        >Press 'Yes'
        <br>
        
        ![warning2](/img/warning2.png "Press 'OK'")
        >Press 'OK'
