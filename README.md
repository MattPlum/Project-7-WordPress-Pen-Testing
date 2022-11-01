# Project 7 - WordPress Pen Testing

Time spent: **10** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pen Testing Report

### 1. Unauthenticated Stored Cross-Site Scripting

- [ ] Summary: 
If a comment is longer than 64KB (the size limit) it will be truncated and result in a malformed HTML resulting in XSS vulnerabilities
  - Vulnerability types: XSS
  - Tested in version: 4.2
  - Fixed in version: 4.2.1
- [ ] GIF Walkthrough: 
    - <img src="https://github.com/MattPlum/Project-7-WordPress-Pen-Testing/blob/f85f896a9208a745c0f5e8948ee676fe14d64500/exp1.gif">
- [ ] Steps to recreate: 
  - Post a comment on a page that has at least of size 64KB which when truncated generates a malformed HTML to inject your payload.
  - View the comment to see the XSS exploit


- [ ] Affected source code:
  - [Link 1](None)
  
### 2.  Authenticated Stored Cross-Site Scripting  

- [ ] Summary: 
The Text editor is a WYSIWYG editor that contains a vulnerability in how it processes shortcode. Similair to first exploit, but requires an authenticated user to create a post
  - Vulnerability types: XSS
  - Tested in version: 4.2
  - Fixed in version: 4.2.3
- [ ] GIF Walkthrough: 
    - <img src="https://github.com/MattPlum/Project-7-WordPress-Pen-Testing/blob/8a63eddf090fa39121a7843e81b8e30ca46f7feb/exp2.gif">
- [ ] Steps to recreate: 
    - Requires contributor or author level account, make a page with the following link. Switch from Visual to Text view: 
    - `<a href=“[caption code=“>]</a><a title=“ onmouseover=alert(‘Vulnerability’) “>link</a>`
- [ ] Affected source code:
  - None

### 3. Widget title XSS

- [ ] Summary: 
  - Vulnerability types: XSS
  - Tested in version: 4.2
  - Fixed in version: 
- [ ] GIF Walkthrough: 
  - <img src= "https://github.com/MattPlum/Project-7-WordPress-Pen-Testing/blob/43708455092516fd77e1c58a876ff1449877b81a/exp3.gif">
- [ ] Steps to recreate: 
  - Login as Admin, go to Appearance -> Customize -> Widgets. Then click Add Widget and select the text option. Enter a title and the payload into the content
  - `<img src="example.com" onerror="alert('xss');"> `
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/changeset/33529)

### 4. User Enumeration at Login

- [ ] Summary: 
  - When trying to login to with a username not in the database, it will return an "Invalid Username" message. When there is a match it will return a different message saying "The password you entered for the username <username> is incorrect. This can give the attacker a list of users through brute force username enumeration
  - Vulnerability types: Enumeration
  - Tested in version: 4.2
  - Fixed in version: Not fixed
- [ ] GIF Walkthrough: 
  - <img src="https://github.com/MattPlum/Project-7-WordPress-Pen-Testing/blob/443283ba59c8589270511e5e11068c70a426b222/exp4.gif">
- [ ] Steps to recreate: 
  - Install Wpscan tool and run command 
  - ' wpscan --url [WORDPRESS_BASE_URL] --enumerate u '
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/branches/4.1/src/wp-login.php)

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)
- [User Enum Vulnerability Discussion]https://www.wpwhitesecurity.com/wordpress-username-disclosure-vulnerability/]
GIFs created with  ...
<!-- Recommended GIF Tools:
[Kap](https://getkap.co/) for macOS
[ScreenToGif](https://www.screentogif.com/) for Windows
[peek](https://github.com/phw/peek) for Linux. -->

## Notes

Describe any challenges encountered while doing the work
  
  WPdistillery was giving a lot of errors. Needed to increase processor size from 1 to 2 in Virtual box of the VM as well as add 192.168.33.10 wpdistillery.vm
to the /etc/hosts file which was not included in the instructions. 

## License

    Copyright [2022] [Matt Lee]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
