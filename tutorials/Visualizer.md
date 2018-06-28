# Visualizer Instructions

Visualizer is implemented with python as a Jupyter notebook. Here, we describe how the tool can be utilized from the AEGIS platform.

## STEP 1(Optional) - Install the notebook

If the Jupyter notebook does not already exist in a specific project, one should first [download](https://www.github.com/aegisbigdata/visualizer) it. Then, upload the Visualizer.ipynb file into Jupyter from the corresponding menu, as seen in figure below

![Upload Notebook](visualizer-screenshots/9.png)

## STEP 2 - Open the notebook

Once the notebook is present, click on it to open. You will see the following:

![Visualizer Initial State](visualizer-screenshots/1.png)

This is the initial state. All code cells are hidden by using the [hide code plugin](https://github.com/kirbs-/hide_code) and also all output has been cleared.

## STEP 3 - Initialize the notebook

Disable code hidding in the first cell by unchecking "Hide Code" box. When the code unfolds, you will see something like this:

![First Cell Code](visualizer-screenshots/0.png)

Then, you should edit the variables **project_user** and **project_name** accordingly. **project_name** is the name of the project currently working with. For the **project_user** variable the rule is a little bit more complex. Username is a string that consists of a total of 8 characters and involves the user's first part of the email (before the @). If this part contains more than 8 characters, the first 8 are used and the rest are truncated. On the contrary, if it less than 8 characters, we fill any remaining empty positions with zeros. Finally, any dot (.) characters are being replaced by underscores (_).
For instance, a user with email testuser@domain.com would have a username "testuser". One with email test.user@domain.com would have a username "test_use" and finally, one with email user@domain.com would have "user0000".

After editing those two variables, hide again the code in the first cell, make sure the cell is selected and either click on the "Run" button from the top Jupyter menu, or press ctrl+enter.

## STEP 4 - Working with the visualizer

Now that everyhting is set, the first widget that appears is something like a file picker, where a user can navigate between the files stored in the current project and open a desired one. Note that currently only CSV files are supported.

![File Picker](visualizer-screenshots/2.png)

Once a file is open, a small preview in tabular format will be shown

![File Preview](visualizer-screenshots/3.png)

Afterwards, a list with the available visualization types will be displayed. Pick a desired type and click on the **Apply** button.

![Visualization Types](visualizer-screenshots/4.png)

For every visualization type, a widget with various options depending on the type will be opened. Fill mandatory fields with the desired values and then click on the **Visualize** button.

![Parameters](visualizer-screenshots/5.png)

![Parameters Filled](visualizer-screenshots/6.png)

Pay attention to the parameter called **Position**. This actually refers to the position on the dashboard that we would like to place the chart to. If you notice in the previous picture, there are five empty cells in the end of the notebook. Those act as placeholders for the dashboard. Currently only up to five different charts at the same time are supported, but this can be easily extended. The dashboard can contain several charts from the same dataset or even from different ones. When a new dataset is openned, previous charts are not deleted.

A sample chart that appers after filling the necessary options can be seen below.

![Sample Scatter Plot](visualizer-screenshots/7.png)

## STEP 5 - Cleaning up

When you have completed your work with the visualizer, it is highly recommended to clear all the output, so you can do a fresh start without any leftovers the next time. This can be achieved from Jupyter's top menu. Choose **Cell -> All Output -> Clear**

![Clear Output](visualizer-screenshots/8.png)

# Important Notes
All the instructions above refer to the Visualizer as a standalone notebook. In future work step 1 will be dropped, since the notebook would we automatically available in every newly created project. Furthermore, when the integration with the other two notebooks takes place(Query Builder, Algorithm Execution Container), step 3 will also be dropped, and the file reading part from step 4 will be utilized from the Query Builder.