Base64Image Plugin for CKEditor 4
=================================

Created by ALL-INKL.COM - Neue Medien Münnich - 04. Feb 2014

Adds images from local client as base64 string into the source without server
side processing. You can also add external image urls into the source.

## Requirements
The Browser must support the JavaScript File API.

## Installation

 1. Download the plugin from http://github.com/stivehu/base64image
 
 2. Either run
```
php composer.phar require --prefer-dist stivehu/base64image "*"
```
or add
```
"stivehu/base64image": "*"
```

 3. Add your composer.json this lines: 
```
  "scripts": {
    "post-update-cmd": [
      "cp -r vendor/stivehu/base64image vendor/ckeditor/ckeditor/plugins/base64image",
      "sed -i 's/^};$/};\\nCKEDITOR.config.extraPlugins = \"base64image\";/g' vendor/ckeditor/ckeditor/config.js",
      "awk -i inplace '!a[$0]++'  vendor/ckeditor/ckeditor/config.js"
    ],
    "post-install-cmd": [
      "cp -r vendor/stivehu/base64image vendor/ckeditor/ckeditor/plugins/base64image",
      "sed -i 's/^};$/};\\nCKEDITOR.config.extraPlugins = \"base64image\";/g' vendor/ckeditor/ckeditor/config.js",
      "awk -i inplace '!a[$0]++'  vendor/ckeditor/ckeditor/config.js"
    ]
  },
```
