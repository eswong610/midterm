# midterm
First section: You must explain the difference between cloning vs fetching vs pulling. Give real world examples of how they differ.

Cloning essentially copies the source code from someone's repository and sets up a local version on your own desktop. The source url will still link back to the repo you cloned 
it from. It will also track any branches cloned from the repo as well. 
Pulling is downloading the changes of the remote repo into 
your local copy and updating any changes that have been made. It essentially does a fetch and merge.
Fetching is similar to pulling because it is the first step of pulling. 
but does not actually change your files in any way. It downloads the files and to see the 
changes if any, but does not actually merge into the local copy so you can be careful about losing any changes you made before doing an actual pull where files are updated. 

A real world example of this would be if I added a style.css file to a project, and another contributor also added a style.css file, then there would be a conflict if i directly pull from the remote repo. I could potentially lose all the changes I made. However if I fetch first, then I could download the differences but it wouldn't affect my local copy, and I could make adjustments based on that. 
An example of cloning would be if there were 3 contributors on a group project and the team leader already has the base foundation (server, html, css) set up on github. The other 2 contributors could just clone the repo into their own desktop to have the same working version and they would be able to make changes to the remote repo as they work so everyone has access to the most updated working version. 

Second section: Create a markdown table that shows the basic differences between Trello and Asana. The list does not need to be exhaustive. Make sure to use a table.

| Asana        | Trello           | 
| ------------- |:-------------:|
| Better dependency management     | can move cards around whenever| 
| team size limit of 15 people (free vrs)     | no team size limit     |  
| uses sections and subtasks as projects grow  | a lot of scrolling as cards stack and no real way to group them |  
| has a calendar and can create timelines | only has a deadline calendar, no timeline |
|Portfolios allow users to manage multiple huge projects at once | More for smaller projects with its simple layout|



Third Section: Answer the following 3 questions:

Question 1: What is the .git folder? Where is the object database in this folder?
The .git folder is created when you initialize a folder as a git repository. It is used to store configuration settings, version control (commits) and addresses that link back to the remote url. The object database in .git is in the object directory. The database stores files as hashes when you do git add and git commit. Each version of a file is stored as a different hash and referencing those when you make changes to a particular commit in history is how it works as a version control. 


Question 2: Explain in detail how the git hash-object function works. 
The git hash object function takes a file, and computes a key that is handed back to you which is the hash value in the SHA-1 hash. This function only returns the hash though and would need extra options to actually store the file, such as -w or stdin which would save the hash into the objects database. Hashing an object is a one way function and cannot be reverted. No matter how big or small the file size is, the hash will always be the same length and in this case of a SHA-1 hash, it will be 160 bits. If you put in the same file/contents, the resulting hash will be the same as a previous hash. 

Question 3: Where does git internally store the file names to our files? How are tree objects related to this?
Git stores it as part of the commit where it is stored in a tree object's content. Git uses blobs to store files of any type but they don't contain file names or paths, but tree objects will show the path and file name. It is essentially a directory for blobs where its content are links to other trees or blobs instead of file text or images. A tree object will show the permissions, data type, hash, and the file name. 