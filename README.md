# FileTree
FileTree is a package that provides two basic functions:

* File tree viewer
The viewer displays a file list as a directory tree in a special buffer.  The file list can be populated from any list of files.  There are functions to populate from a number of common sources: recentf, files in buffer-list, files in the current directory, files found recursively in the current directory.  Within the viewer, the file list can be filtered and expanded in various ways and operations can be performed on the filtered file list (e.g., grep over files in list).

* File notes
The file notes enables the user to write and display (org-mode) notes associated with individual files and directories.  The note can be displayed in a side buffer either when cycling through files in the file tree viewer or when the file is open in a buffer.  The notes are kept in a single org-mode file with a heading for each file/directory.

## Motivation
FileTree started as a way to more easily select files from recentf-list.  The tree structure view and basic filtering operations helped to quickly narrow to the file of interest.  Over time, I've found the structure to be a convenient foundation for building additional functionality for my workflow around.  

## File Tree Viewer

### Starting and Exit Viewer
The following commands start the viewer with the corresponding file list
| Command                        | Comment                                       |
|--------------------------------|-----------------------------------------------|
| fileTree-showRecentfFiles      | populate files from recentf-list              |
| fileTree-showCurDir            | populate files from current dir               |
| fileTree-showCurDirRecursively | populate files from current dir (recursively) | 
| fileTree-showCurBuffers        | populate files from buffer-list               |
| fileTree-showFiles             | populate files from file list in argument     |
| fileTree-recentf-cancel-dialog | exit viewer (tied to q in keymap              |


### Navigation
Within the *FileTree* window the following navigation commands can be used
| Command              | key map     | Comment         |
|----------------------|-------------|-----------------|
| fileTree-next-line   | down, j     |                 | 
| fileTree-prev-line   | up, k       |                 | 
| fileTree-next-branch | SPC         |                 | 
| fileTree-prev-branch | TAB         |                 |

### Filtering, Expanding and View modes
| Command                       | key map | Comment                              |
|-------------------------------|---------|--------------------------------------|
| fileTree-filter               | f       |  <ADD>                               |
| fileTree-expandDir            | e       |  Add files in directory at point     |
| fileTree-expandDirRecursively | E       |  Add files in directory at point recursively |
| fileTree-reduceListBy10       | -       |                                      | 
| fileTree-pop-fileListStack    | b       | undo prev filter/expansion operation |
| fileTree-set-maxDepth         | 0-9     | set max depth of tree to view 0=max  |
| fileTree-cycle-maxDepth       | /       | cycle through max depth              |
| fileTree-ttoggle-flat-vs-tree | .       | toggle between tree and flat view    |
Selecting (by pressing RETURN or clicking) on a file in the FileTree buffer opens the file.  Selecting on a directory narrows to the chosen subtree.


### Operations
| Command              | key map | Comment                         |
|----------------------|---------|---------------------------------|
| fileTree-grep        | g       | grep over files in current list |
| dired                | d       |                                 |

### Customizations


## File Notes





