# Jekyll Static Site Builder

## Steps to update the site

### Step 1:
Run `gem install jekyll`

### Step 2:
Clone this repo `https://bitbucket.org/richmediateam/richmedia-static-pages`

### Step 3:
Run `npm install` from the folder.

### Step 4:
Run `gulp` and it will generate the site and open up `http://localhost:3000/`

This will create an `_site` folder with all static html ans assets.

***

## Push `_site` files & folders into richmediateam.bitbucket.org

```
# Go to the folder
> cd folder

# Initiate Git
> git init

# Add all subfolders & files
> add .

# Make the commit
> git commit -m 'Initial commit'

# Add the remote BitBucket folder
> git remote add origin https://bitbucket.org/richmediateam/richmediateam.bitbucket.org

# Push stuff to BitBucket
> git push -u origin master 
```
