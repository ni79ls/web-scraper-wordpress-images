# Free Site to Site Migration Script for Wordpress

This script will help you to migrate posts, pages including a large volume of images from one Wordpress site to another without the use of any (paid) Wordpress migration plug-ins.

The full Medium article is available [here](https://medium.com/gitconnected/free-large-volume-wordpress-site-to-site-migration-of-images-and-posts-d5b3e6cdb71d).

**Prerequisites:**

1. You have exported the posts, pages, comments, ... from your current Wordpress site via the standard `Wordpress Tools -> Export` functionality
2. You have installed the free plugin https://wordpress.org/plugins/media-sync/ (or similar) on your target Wordpress site

**Key steps of the script:**

- You need to manually define the input file name(s) and local output folder(s) as variables at the beginning of the script (`chapter 0 - Set Variables`)
- The script automatically identifies all potential image URLs (`chapter 2 - Extract Image URLs`)
- The script downloads all identified images into the earlier specified folder (`chapter 3 - Download all Images`)
- The script modifies the original image URLs within the Wordpress export xml file and replaces it with the newly generated image file name and location (`chapter 4 - Replace Original Image URLs with new Image URLs`)

**Output after executing the script:**

- All identified images are stored locally in the folder that you specified
- A copy of the original Wordpress export xml file including the modified / new image urls is stored locally

**Todo after script has executed:**

- You must now manually upload all your downloaded images into the target folder of your target Wordpress installation that you specified at the beginning of this notebook (e.g. via FTP client)
- Import the newly generated Wordpress xml file via the standard `Wordpress Tools -> Import` functionality
- Don't forget to refresh the media library in Wordpress (e.g. using this plugin: https://wordpress.org/plugins/media-sync/)
