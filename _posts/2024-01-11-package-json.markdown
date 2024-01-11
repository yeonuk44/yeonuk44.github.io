---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_package_json
title: About package.json
# title: About package.json
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Javascript
# multiple tag entries are possible
tags: [javascript]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-01-11 09:00:00 +0900
# seo
# if not specified, date will be used.
#meta_modify_date: 2021-08-10 11:32:53 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# please use the "image_viewer_on" below to enable image viewer for individual pages or posts (_posts/ or [language]/_posts folders).
# image viewer can be enabled or disabled for all posts using the "image_viewer_posts: true" setting in _data/conf/main.yml.
#image_viewer_on: true
# please use the "image_lazy_loader_on" below to enable image lazy loader for individual pages or posts (_posts/ or [language]/_posts folders).
# image lazy loader can be enabled or disabled for all posts using the "image_lazy_loader_posts: true" setting in _data/conf/main.yml.
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---

<!-- outline-start -->

## About "package.json"

Today I'd like to write about an install error that can occur when merging files, based on my experience.

I sometimes swap package.json files when I need to match a dependency module with another team member.

Of course, if you have a collaborative environment with git, there are other good options, but sometimes you have to go with the next best thing if you can't do the best thing.

Let's say I'm in that situation.

In my case, I've found that sometimes I need to manually install dependency packages that are listed in the package.json inside my project, even though they should all be installed when I type the npm install command.

Today, we'll look at this issue.

{:data-align="center"}

<!-- outline-end -->

### Why do I sometimes need to manually install?

1. your package.json file has changed and you didn't run npm install: If a dependency package has been added or updated to your package.json file, you'll need to run npm install to apply those changes. After making changes to your package.json file, you'll need to run the npm install command again to install the package.
2. If the node_modules directory has been deleted: When you run the npm install command, the packages are installed in the node_modules directory. If the node_modules directory was manually deleted, you will need to run npm install again to install the packages again.
3. package-lock.json file conflict: The package-lock.json file is used to record the exact version of a package's dependencies. When sharing or collaborating on a project, other developers may change the package-lock.json file or cause conflicts. In this case, you should update or delete the package-lock.json file before running the npm install command.
4. Network issues: Sometimes you may not be able to download a package due to network connectivity issues. In this case, we recommend checking your network connection and rerunning npm install.

Dependency packages may not install automatically due to these reasons.

If you find yourself in one of the above situations, you will need to install the packages manually to resolve the issue.

### Conclusion

Dependency packages may not install automatically for any of these reasons.

If you find yourself in one of the above situations, you'll need to install the packages manually to resolve the issue.
