# Project 7 - WordPress Pen Testing

Time spent: **X** hours spent in total

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
  
### 2. (Required) Stored XSS

- [ ] Summary: 
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

### 3. (Required) Vulnerability Name or ID

- [ ] Summary: 
  - Vulnerability types:
  - Tested in version:
  - Fixed in version: 
- [ ] GIF Walkthrough: 
- [ ] Steps to recreate: 
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

### 4. (Optional) Vulnerability Name or ID

- [ ] Summary: 
  - Vulnerability types:
  - Tested in version:
  - Fixed in version: 
- [ ] GIF Walkthrough: 
- [ ] Steps to recreate: 
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

### 5. (Optional) Vulnerability Name or ID

- [ ] Summary: 
  - Vulnerability types:
  - Tested in version:
  - Fixed in version: 
- [ ] GIF Walkthrough: 
- [ ] Steps to recreate: 
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with  ...
<!-- Recommended GIF Tools:
[Kap](https://getkap.co/) for macOS
[ScreenToGif](https://www.screentogif.com/) for Windows
[peek](https://github.com/phw/peek) for Linux. -->

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
