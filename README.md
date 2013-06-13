# FreshDesk.com PHP API Wrapper

Originally wrote this tool to import all of my KB articles from SugarCRM Knowledgebase.
So, it originally was just methods creating solutions.  It's since been expanded to support user creation, company creation, and even avatar creation!
This api wrapper also serves as a good reference as it uses several undocumented API methods / features.


## Highlights

### Provides methods that are useful for creating articles.

1. Facilitates creating solutions by allowing the use of strings instead of looking up category ids / folder ids / topics ids.
2. When creating an article which has a folder name or category name that doesn't exist, they can be created automatically.
3. Caches folder and category id's so they don't have to be looked up on subsequent operations.  But, this is abstracted from you.


### User Avatar Creation
See this blog post: <http://www.blakerobertson.com/devlog/2013/6/13/generating-an-avatar-for-customers-with-a-splash-of-utility.html>

In the samples folder you'll find a script which you can run from the command line and it'll create an avatar icon for each of your customers.
The avatar will consist of the customers initials + a color bar which is common to the company.


## Ways To Improve
1. Error handling is ok, but could be improved.
2. Not 100% consistent with return types, check method comments.

## Usage
1. Copy the FreshdeskRest.php into your project.
2. Here's some code.

```
<?php

require_once("FreshdeskRest.php");
$fd = new FreshdeskRest("yoursubdomain.freshdesk.com", "your_username", "your_password");
$fd->setCreateStructureMode('true'); // will create categories and folders if they don't exist.

$fd->createOrUpdateArticle("TEST CATEGORY", "Test_Folder", "Test Article Title", "The <u>HTML</u> of your body goes here!<P>Paragraph 2</P>");
```

![gitimg](https://gitimg.com/blak3r/freshdesk-solutions/README/track)
