 # Hugo

## Install Hugo
sudo apt-get install hugo

## Hugo commands

Go to your project folder and creates a new site 
```
hugo new site <name-project>
```
Initialize the repo
```
git init
```
Launch the server Hugo so you can open it in your http://localhost:1313
```
hugo server
```

Create new content, like for instance:
+ A new chapter:
```
hugo new --kind chapter hugo/_index.md
```

+ A new entry:
```
hugo new hugo/quick_start.md
```

