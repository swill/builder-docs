---
title: Contribute
weight: 1000
---

The content of this website is maintained on Github at [github.com/swill/builder-docs](https://github.com/swill/builder-docs), please feel free to contribute.  We will do our best to keep the content up-to-date with the functionality, but 100% coverage of the features will be a work in progress.


## How to Contribute

To contribute, you will need to fork the Github repository [github.com/swill/builder-docs](https://github.com/swill/builder-docs), and make changes in your own fork.  
![github_fork][github_fork]

Changes can be done by editing the files directly in the Github UI in your fork.  
![github_edit][github_edit]

Once finished editing the files, you will need to commit your changes.
![github_commit][github_commit]

Once finished making changes, create a new Pull Request to submit the changes back to `swill`s repository.  

Click the `New Pull Request` button on the `Pull Requests` tab.
![github_create_pr][github_create_pr]

Click the `Create Pull Request` button to submit the changes to my repository.

![github_submit_pr][github_submit_pr]

Once the pull request has been reviewed, it will be approved and the changes will get published to the live site.


## Content Layout

Each page has its own Markdown file in the `./content/` directory.  The name of the file will be used as the URL slug, so please use hyphens (`-`) if you need a separator.

Each page has some metadata at the top of the Markdown file.  More details can be found in the [`front matter` documentation](https://gohugo.io/content/front-matter/) for Hugo, but the main ones to note are the following:

``` yaml
---
title: The Page Title
weight: 50
---
```

The `title` will be the title of the page.
The `weight` is used to determine the page order.

Review the other pages to better understand what values to use for the `weight`.


## Menu Entries

The top level menu entries on the left are manually specified in the `./config.toml` file.  The sub-menu items are automatically created based on the header elements on that page.

You would place something like the following in the menu section of the `./config.toml` file.

``` toml
[[menu.main]]
	name   = "New Top Level Menu"
	url    = "page-url/"
	weight = 50
```

{{< note title="Note" >}}
The trailing `/` is required for all links so I have more hosting options.
{{< /note >}}


[github_fork]: /images/contribute/github_fork.png "Fork on Github"
[github_edit]: /images/contribute/github_edit.png "Edit on Github"
[github_commit]: /images/contribute/github_commit.png "Commit change"
[github_create_pr]: /images/contribute/github_create_pr.png "Create Pull Request"
[github_submit_pr]: /images/contribute/github_submit_pr.png "Submit Pull Request"