# Install

1. run `./scripts/setup` to install the dependencies. You only have to run this once!

**Note:** To update the dependencies, run `./scripts/update`

# Cook a New Book

1. run `./scripts/fetch-book statistics ${ID}`
  - **Example:** `./scripts/fetch-book statistics 69619d2b-68f0-44b0-b074-a9b2bf90b2c6@11.330`
  - **Note:** This will require you to log in via ssh. Also, make sure the **ID** contains the version.
  - **Note:** your can set the ssh username by running `USER=myusername ./scripts/fetch-book ...`
1. run `./scripts/bake-book statistics`

There are 2 major parts to cooking a book (_listed above_). You will first need to get the single-file HTML from the server (`fetch-book`) and then convert the single-file HTML locally into the "baked" book via `bake-book`. Once you have done the first part, you can run `./scripts/bake-book statistics` to your :heart:'s content!


## Add a New Book to the config

Sometimes you need to add a new book (like "dark-matter") into this repo. Here are the steps to add it:

1. Find the UUID of the book you want
  - point your browser to `cte-cnx-dev.cnx.org` and find a book you want.
  - click "More Information" and copy the **ID**
1. add an entry to `./books.txt`


# Test

1. run `./scripts/test`

This will run the linter, generate sassdocs, and generate the guides to verify they work.

# Documentation

1. run `./scripts/generate-docs` to generate the SASS Docs
1. run `./scripts/generate-guide statistics` to generate the HTML Guide for a book
1. open the generated file in your browser

## CSS Coverage

1. run `./scripts/fetch-book ${BOOK_NAME} ${UUID}` to fetch the Raw HTML for a book
1. run `./scripts/report-book-coverage ${BOOK_NAME}` to generate the CSS Coverage file
1. run `genhtml ...` (exact output is shown in the previous step) to generate an HTML report


## Experimental

To update the Documentation in the gh-pages branch:

1. `git checkout master`
1. `./scripts/generate-and-update-gh-pages`

**Note:** This will push changes if successful
