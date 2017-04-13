---
title: "My first R package"
author: "Dinesh Poddaturi"
topic: "10"
layout: post
root: ../../../
---
This is the first time I wrote an R package. Working with a team helped me understand it very well. Our team did a good job building a small R package (LittleChickens). We followed all the instructions from the notes to build the package. 

It took us some trial and errors syncing the github repository to the R workspace, pushing and pulling code changes. Now I am comfortable syncing the repository and I am planning to use this technique in my project.  By doing so we can avoid sending/sharing code through emails or Dropbox.

We encountered some issues with the data we used in the package. We saved our data as .Rda instead of .rda extension. After changing the extension, our function read the data successfully. We saved our chicks data in the R workspace using ‘save()’. Later we realized this command would save the data into the object ‘data’ instead of ‘Chicks’. After changing the data object we were able to fix all the issues related to data. 

In the future, I would save data carefully, write documentation for every function, write ample of examples, and follow all the other necessary steps to build a package.

