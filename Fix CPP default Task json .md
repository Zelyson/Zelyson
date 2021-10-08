# How to fix default CPP buld task not including workspaceRoot as include folder for said default CPP build task:

1. Go here: `C:\Users\$USER$\.vscode\extensions\ms-vscode.cpptools-1.7.0-insiders2\dist`
2. Edit main.js in line ~47600 where it says: `-fdiagnostics-color=always`
3. edit [] to: `['-fdiagnostics-color=always', '-g', '-I', '${workspaceRoot}', '${file}', '-o', filePath + (isWindows ? '.exe' : '')]`
(Add: '-I', `${workspaceRoot}`,)

Done!

This bugged me since I would expect a CPP build Task to include The main.cpp folder to look for header files.
