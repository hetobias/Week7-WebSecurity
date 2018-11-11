# Project 7 - WordPress Pentesting

Time spent: **6** hours spent in total

> Objective: Find, analyze, recreate, and document **three** affecting an old version of WordPress

## Pentesting Report

1. (Required) Authenticated Cross-Site Scripting (XSS)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.6
  - [x] GIF Walkthrough: ![](https://github.com/hetobias/Week7-WebSecurity/blob/master/authenticated%20cross-site%20scripting%20xss.gif)
  - [x] Steps to recreate: 
  - 1. Create or go to exisiting post, make sure you are able to comment on it.
  - 2. Copy and paste this: ```=<svg onload=alert("hello_world")>``` into the comment section
  - 3. Click "Post Comment"
  - [x] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/7ab65139c6838910426567849c7abed723932b87)
2. (Required) Authenticated Shortcode Tags XSS
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.2
  - [x] GIF Walkthrough: ![](https://github.com/hetobias/Week7-WebSecurity/blob/master/shortcode%20tag%20xss.gif)
  - [x] Steps to recreate: 
  - 1. Create or go to exisiting post, make sure you are able to comment on it.
  - 2. Copy and paste this : ```<a href = "XSS" onmouseover=alert("hello") rel="nofollow">try me</a>``` into the comment section
  - 3. Click "Post Comment" put your mouse over "try me" on the new comment.
  - [x] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/f72b21af23da6b6d54208e5c1d65ececdaa109c8)
3. (Required) User Enumeration
  - [x] Summary: 
    - Vulnerability types: User Enumeration
    - Tested in version: 4.2
    - Fixed in version: 4.4
  - [x] GIF Walkthrough: ![](https://github.com/hetobias/Week7-WebSecurity/blob/master/user%20enumeration.gif)
  - [x] Steps to recreate: 
  - 1. Go to the login page for WordPress
  - 2. Enter a random username and password, it should tell you if the username exists or not.
  - 3. Enter a existing username (admin) and enter a wrong password. It should tell you the password was wrong for "admin".
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

I encountered a problem while trying to access pages and posts that are created in WordPress which I fixed by going to the settings tab in admin and change the routes of the permalinks. 

## License

    Copyright [2018] [Tobias He]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
