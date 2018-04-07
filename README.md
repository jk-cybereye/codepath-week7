# codepath-week7
Spring 2018 Codepath Week7 challenge

## Pentesting Report
Spring 2018 Codepath Week7 challenge
Project 7 WordPress Pentesting

Time spent: **50+** hours spent in total
Breakdown of excessive hours !
    
    Win 7 Pro x64 - Installation of WMF 4/5.1 for powershell.                 2 hrs
                - Installation of vagrant successfully 3 attempts             10 hrs  ( 1 hr x 3 plus debugging)
                - Virtualbox installation on Win 7                            1 hr
                - Getting VP 4.2 and VirtualBox Kali to ping each other..     20 hrs
                    There were a number of problems. Unable to view WP page
                    with host browser (FF 52 ESR  or Chrome 57)     
    Ubuntu 14.04- Installation of vagrant / virtual box w ext                 3 hrs
                - Intallaticon of Wine (installation crashed) required        10 mhrs
                - extensive cleanu of Ubuntu packages that were damaged
                - Finally sudo dpkg –configure -a. 
                  sudo apt-get install -f.  

## Pentesting Report
<img src="file.gif"> <img src="my_gif_walkthrough_url" width="800">
1. (Required) Vulnerability Name is Cross-site scripting
  - [ ] Summary: 
    - Vulnerability types:  Cross site scripting
    - Tested in version: 4.2
    - Fixed in version: 4.7.5
  - [ ] GIF Walkthrough: <img src='Week 7xss.gif'/>
  - [ ] Steps to recreate: 
 I logged into wordpress as admin.http://wpdistillery.vm/wp-admin
  I went to a page I created.  In the comment section I wrote the following xss <svg/onload-alert('XSS')
  - [ ] Affected source code: http://klikki.fi/adv/wordpress2.html      CVE-2015-3440
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
  - [ ] Summary: 
  
  2. - Vulnerability types:  large Media file with XSS
    - Tested in version: 4.2
    - Fixed in version: 4.7.3
  - [ ] GIF Walkthrough: <img src='Largeuploadxss.gif'/>
  - [ ] Steps to recreate: I downloaded a large image file from the internet.  One that was more than 2mb. I changed the name of the file to what I wanted to inject.  I logged into wordpress as admin.http://wpdistillery.vm/wp-admin and went to the media page where I dragged my large file with the name <svg onload='alert(228)'>
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
  
3. (Required) Vulnerability Name is Denial of Service DOS, CVE-2018-6389
  - [ ] Summary: an attack that forces an end user to execute unwanted actions on a web application in which they're currently authenticated
    - Vulnerability types:
    - Tested in version:4.2
    - Fixed in version: 4.9
  - [ ] GIF Walkthrough: <img src='crecords.gif'/>
  - [ ] Steps to recreate: Went to a site https://baraktawily.blogspot.fr/2018/02/how-to-dos-29-of-world-wide-websites.html to learn how to attack my WordPress site.
 Used the doser.py to attack my WordPress and I put that file on my desktop in Linux.
  I pasted a long script from the site onto the commandline in Linux but changed the script so that it pointed to my WordPress site.
  Then I loaded the doser.py and went back to my script.  When I executed the script, I went to WordPress and I found that I couldn't manipulate the site anymore.
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2018] [Sandy Keh]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
