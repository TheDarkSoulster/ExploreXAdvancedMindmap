Open sourced advanced Mindmap View in the ExploreX App.
# Requirements
--
A simple webserver and PHP (Version 5 or above) if you want to save public mindmaps. Otherwise PHP is not needed.

Extract the files and place it in the root directory of your website.

'S3' folder is used to save the public mindmap files. If you are in linux, make that folder writable, ie, chmod 666

# i. Google Drive

Note: This sign-in will not work after February 6, 2023. Google is making changes. Goto the link below to know more about it.
https://developers.googleblog.com/2021/06/upcoming-security-changes-to-googles-oauth-2.0-authorization-endpoint.html

How to setup Google Drive:
a. Setup apiKey, clientId, appId from Google Cloud console. Use your website name. Goto https://console.cloud.google.com/
b. Open js/GoogleDrive.js
c. Fill in 'apiKey, clientId, appId' which you obtained from the step, a.

# ii. S3 storage (public storage)
Make sure there is 'S3' folder in the root path. Make sure it contains two php files, process.php and processFilenames.php . Make 'S3' folder writable. If you are in linux, make that folder writable, ie, chmod 666
Edit 'js/Config.js' and replace 'yourwebsite.com' with your website url.

# iii. Sharemap.js
To share your public map via Facebook, do the following changes.

a. Create an App in facebook. Make sure your website is allowed as origin.

Open Sharemap.js and make the following changes.
a. Locate this line (number 28) and change https://www.facebook.com/dialog/feed?app_id=11111111&'
to app_id='With your facebook app id'

b. Change http://mindmapmaker.org/mind-map-maker.png (on line number 32) to your website
c. Change https://app.mindmapmaker.org (on line number 34) to your website

# iv. UrlShortener.js
To share map via 'bit.ly' make changes in js/UrlShortener.js
//Register for an account at bit.ly/a/sign_up
Change 'var username="";' (on line number 12) with your username from bit.ly
Change 'var actoken="";' (on line number 13) with your actoken from bit.ly

# v. googledrive.php
googledrive.php file is used to open a file from Google Drive where you previously saved. 
Open 'googledrive.php' file and change https://yourwebsite.com/ to your website.


Use the following nginx configuration too. My webserver is 'nginx'. This configuration works for nginx. If you use apache, you need to change the configuration.

//////
	if ($arg_state) {
	  set $test  P;
	}
	
	if ($uri !~ /googledrive\.php$) {
		set $test  "${test}C";
	}

	if ($test = PC) {
	 rewrite ^.*$ googledrive.php permanent;
	}
/////


Make the most out of this project!
\ By Saket Dhulipala /

---
<h1 align="center">Hi 👋, I'm Saket Dhulipala</h1>
<h3 align="center">A passionate frontend developer and Graphic Designer from India</h3>

<p align="left"> <a href="https://github.com/ryo-ma/github-profile-trophy"><img src="https://github-profile-trophy.vercel.app/?username=thedarksoulster" alt="thedarksoulster" /></a> </p>

<h3 align="left">Connect with me:</h3>
<p align="left">
<a href="https://dev.to/thedarksoulster" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/devto.svg" alt="thedarksoulster" height="30" width="40" /></a>
<a href="https://kaggle.com/saketdhulipala" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/kaggle.svg" alt="saketdhulipala" height="30" width="40" /></a>
<a href="https://instagram.com/saket.dhulipala" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="saket.dhulipala" height="30" width="40" /></a>
<a href="https://www.youtube.com/@saketdhulipala" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/youtube.svg" alt="@saketdhulipala" height="30" width="40" /></a>
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://developer.android.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/android/android-original-wordmark.svg" alt="android" width="40" height="40"/> </a> <a href="https://www.arduino.cc/" target="_blank" rel="noreferrer"> <img src="https://cdn.worldvectorlogo.com/logos/arduino-1.svg" alt="arduino" width="40" height="40"/> </a> <a href="https://www.gnu.org/software/bash/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/gnu_bash/gnu_bash-icon.svg" alt="bash" width="40" height="40"/> </a> <a href="https://www.chartjs.org" target="_blank" rel="noreferrer"> <img src="https://www.chartjs.org/media/logo-title.svg" alt="chartjs" width="40" height="40"/> </a> <a href="https://www.w3schools.com/css/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3" width="40" height="40"/> </a> <a href="https://www.djangoproject.com/" target="_blank" rel="noreferrer"> <img src="https://cdn.worldvectorlogo.com/logos/django.svg" alt="django" width="40" height="40"/> </a> <a href="https://www.figma.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="figma" width="40" height="40"/> </a> <a href="https://firebase.google.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/firebase/firebase-icon.svg" alt="firebase" width="40" height="40"/> </a> <a href="https://cloud.google.com" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/google_cloud/google_cloud-icon.svg" alt="gcp" width="40" height="40"/> </a> <a href="https://git-scm.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="git" width="40" height="40"/> </a> <a href="https://www.w3.org/html/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="40" height="40"/> </a> <a href="https://www.adobe.com/in/products/illustrator.html" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/adobe_illustrator/adobe_illustrator-icon.svg" alt="illustrator" width="40" height="40"/> </a> <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript" width="40" height="40"/> </a> <a href="https://kotlinlang.org" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/kotlinlang/kotlinlang-icon.svg" alt="kotlin" width="40" height="40"/> </a> <a href="https://www.linux.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" alt="linux" width="40" height="40"/> </a> <a href="https://www.mysql.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="mysql" width="40" height="40"/> </a> <a href="https://nextjs.org/" target="_blank" rel="noreferrer"> <img src="https://cdn.worldvectorlogo.com/logos/nextjs-2.svg" alt="nextjs" width="40" height="40"/> </a> <a href="https://www.nginx.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nginx/nginx-original.svg" alt="nginx" width="40" height="40"/> </a> <a href="https://nodejs.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="nodejs" width="40" height="40"/> </a> <a href="https://nuxtjs.org/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/nuxtjs/nuxtjs-icon.svg" alt="nuxtjs" width="40" height="40"/> </a> <a href="https://www.photoshop.com/en" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/photoshop/photoshop-line.svg" alt="photoshop" width="40" height="40"/> </a> <a href="https://www.postgresql.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg" alt="postgresql" width="40" height="40"/> </a> <a href="https://pytorch.org/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/pytorch/pytorch-icon.svg" alt="pytorch" width="40" height="40"/> </a> <a href="https://reactjs.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="react" width="40" height="40"/> </a> <a href="https://www.tensorflow.org" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/tensorflow/tensorflow-icon.svg" alt="tensorflow" width="40" height="40"/> </a> <a href="https://www.typescriptlang.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" alt="typescript" width="40" height="40"/> </a> <a href="https://vuejs.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vuejs/vuejs-original-wordmark.svg" alt="vuejs" width="40" height="40"/> </a> <a href="https://vuepress.vuejs.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/AliasIO/wappalyzer/master/src/drivers/webextension/images/icons/VuePress.svg" alt="vuepress" width="40" height="40"/> </a> <a href="https://www.adobe.com/products/xd.html" target="_blank" rel="noreferrer"> <img src="https://cdn.worldvectorlogo.com/logos/adobe-xd.svg" alt="xd" width="40" height="40"/> </a> <a href="https://zapier.com" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/zapier/zapier-icon.svg" alt="zapier" width="40" height="40"/> </a> </p>

<h3 align="left">Support:</h3>
<p><a href="https://www.buymeacoffee.com/saket.dhulipala"> <img align="left" src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="50" width="210" alt="saket.dhulipala" /></a></p><br><br>

<p><img align="center" src="https://github-readme-stats.vercel.app/api/top-langs?username=thedarksoulster&show_icons=true&theme=dark&title_color=ffffff&text_color=e1e1e1&locale=en&layout=compact" alt="thedarksoulster" /></p>

<p><img align="center" src="https://github-readme-streak-stats.herokuapp.com/?user=thedarksoulster&" alt="thedarksoulster" /></p>
