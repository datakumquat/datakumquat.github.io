---
layout: post
title:  "Load Jupyter Session"
date:   2023-01-29 12:30:45 +1300
categories: blog update
---
In the previous article, [Start Jupyter Notebook], you saw how to start your Anaconda session on Ubuntu using the Activities menu, then invoke a new Jupyter Notebook using the shell.

Once the Jupyter Notebooks load, the new UI looks like this:

![Screenshot image of Jupyter Notebook Server Main UI](/assets/img/Jupyter_Notebook_Main_UI_2023-02-04.png)

The default view is the FILES view, with sub-views available of:

  - Running
  - Clusters

In the top right, you will note the [QUIT] and [LOGOUT] buttons, that do exactly as labelled.

Just below [LOGOUT], you will see:

  - [UPLOAD]
  - [NEW]

If you select [NEW], there will be a further 4 options:

  - Python 3 (ipykernel)
  - Text File
  - Folder
  - Terminal

Let's select New > Terminal first, which will load a Terminal via the web browser located:

[http://localhost:8888/terminals/2]

![Screenshot image of Jupyter Notebook Server New Terminal](/assets/img/Jupyter_Notebook_New_Terminal_2023-02-04.png)

Next, lets select New > Folder, which will create a new folder in the current directory which is /home/dk, and the folder will be titled 'Untitled Folder.'

![Screenshot image of Jupyter Notebook Server New Untitled Folder](/assets/img/Jupyter_Notebook_New_Untitled_Folder_2023-02-04.png)

Lets delete that folder, by using the left hand select button next to 'Untitled Folder' and then selecting the Trash Can item up in the directory overview.

![Screenshot image of Jupyter Notebook Server New Delete Untitled Folder](/assets/img/Jupyter_Notebook_New_Delete_Untitled_Folder_2023-02-04.png)

Lets select New > Text File, which will load a Text file, titled 'untitled.txt' via the web browser located:

[http://localhost:8888/edit/untitled.txt]

![Screenshot image of Jupyter Notebook Server New Untitled Text File](/assets/img/Jupyter_Notebook_New_Untitled_Text_File_2023-02-04.png)

Finally, lets select New > Python 3 (ipykernel), which load a new Python 3 (ipykernel) session via the web browser, located:

[http://localhost:8888/notebooks/Untitled2.ipynb?kernel_name=python3]

![Screenshot image of Jupyter Notebook Server New Python3 Ipykernel Session](/assets/img/Jupyter_Notebook_New_Python3_Ipykernel_Session_2023-02-04.png)

The Jupyter Notebook allows a great deal of flexibility and power from the Desktop using a web browser.

For further information, refer to the [Jupyter/IPython Notebook Quick Start Guide].

Good luck, and have fun!

**References:**

  - [Start Jupyter Notebook]
  - [QUIT]
  - [LOGOUT]
  - [UPLOAD]
  - [NEW]
  - [http://localhost:8888/terminals/2]
  - [http://localhost:8888/edit/untitled.txt]
  - [http://localhost:8888/notebooks/Untitled2.ipynb?kernel_name=python3]
  - [Jupyter/IPython Notebook Quick Start Guide]

[Start Jupyter Notebook]: https://datakumquat.github.io/blog/update/2023/01/27/start-jupyter-notebook.html
[QUIT]: https://datakumquat.github.io/
[LOGOUT]: https://datakumquat.github.io/
[UPLOAD]: https://datakumquat.github.io/
[NEW]: https://datakumquat.github.io/
[http://localhost:8888/terminals/2]: http://localhost:8888/terminals/2
[http://localhost:8888/edit/untitled.txt]: http://localhost:8888/edit/untitled.txt
[http://localhost:8888/notebooks/Untitled2.ipynb?kernel_name=python3]: http://localhost:8888/notebooks/Untitled2.ipynb?kernel_name=python3
[Jupyter/IPython Notebook Quick Start Guide]: https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/#jupyter-ipython-notebook-quick-start-guide
