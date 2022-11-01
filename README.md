# Project 7 - WordPress Pen Testing

Time spent: 12 hours spent in total

> Objective: Find, analyze, recreate, and document **three vulnerabilities** affecting an old version of WordPress

## Pen Testing Report

### 1. (Required) WordPress <= 4.2.2 - Authenticated Stored Cross-Site Scripting (XSS)

- [ ] Summary: Inserting an infected Javascript code to a post can take over the website. 
  - Vulnerability types: Cross Site Scripting (XSS)
  - Tested in version: 4.2
  - Fixed in version: 4.2.3
- [ ] GIF Walkthrough:
- [ ] ![real1 exploit](https://user-images.githubusercontent.com/112200901/199351659-6cac35cc-c7e3-4d15-95f7-5fc3515dddbb.gif)


- [ ] Steps to recreate: 1. I created a post and entered the infected code in the subject line. 
-  2. Save the Draft
-  3. Preview the File
-  4. The message Got Ya! should appear. 
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
  
### 2. (Required) Cross Site Scripting Media File

- [ ] Summary: An attacker can add a JavaScript code onto an image on WordPress so that when it's uploaded, it runs the code. 
  - Vulnerability types:Cross-Site Scripting (XSS)
  - Tested in version: 4.2
  - Fixed in version: 4.6.1
- [ ] GIF Walkthrough: ![Second exploit](https://user-images.githubusercontent.com/112200901/199351742-14aca5d0-dbb5-4006-804d-75c620f993fb.gif)

- [ ] Steps to recreate: 1. Save an image file 2. Rename it and add the code 3.preview the page 4. A message should Pop up
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

### 3. (Required) WordPress <= 4.3 -Authenticated Shortcode Tags Cross-Site Scripting (XSS)

- [ ] Summary: Unwanted users can add an infected web script during processing of shortcode tags. 
  - Vulnerability types:Cross-Site Scripting (XSS)
  - Tested in version: 4.2.2
  - Fixed in version: 4.3.1
- [ ] GIF Walkthrough: ![3exploit](https://user-images.githubusercontent.com/112200901/199354407-e50d9d61-b6a6-4e48-a126-a5d3acbe0355.gif)

- [ ] Steps to recreate: 1. Create a post and add the infected code to the body. 2. Preview the Post 3. Click on the "click me" link. 4. A message box should pop up. 
- [ ] Affected source code: media.php
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

## Assets
-Downloaded Plug-ins on my website 


## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with  ...
<!-- Recommended GIF Tools:

[ScreenToGif](https://www.screentogif.com/) for Windows


## Notes

The biggest challenge for me was being able to run the WPScan for vulnerabilities. When I kept executing the scan on my Kali machine, I was only getting one vulnerability. I ended up destroying everything and started from scratch again. I am not sure what I missed the first time. 

## License

    Copyright [2022] [Leslie Carbajal]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
