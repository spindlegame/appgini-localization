# AppGini Localization Project
This project is not more than an idea at the moment. I try to convert AppGini in a multilingual app, following the model of OSCommerce.

# Idea
I am developping a multilingual app with AppGini and try to make it multilingual in a seamless way, for all envolved: programmers, administrators and users.
The model I have in mind is OSCommerce use of language specific files which hook into the base files for each page.
AppGini has somethings similar with its files in the hook folder.

# Delimitation
Just to make it clear, the generic texts for the App's __user interface__ are largely translated, such as buttons. What is missing is a translation for the custom made fields.
This is neither about automatic language detection. Solutions for this have already been provided.

# References
AppGini Software: https://bigprof.com/appgini/
AppGini on Github: https://github.com/bigprof-software
AppGini User Interface Localization: https://bigprof.com/appgini/help/localizing-appgini-applications
AppGini Forum Discussions on Localization: https://forums.appgini.com/phpbb/viewtopic.php?t=4129
AppGini Forum Discussions on automatic language detection:https://forums.appgini.com/phpbb/viewtopic.php?t=3059

OSCommerce: https://www.oscommerce.com/Products&Download=oscom2341
OSCommerce on Github: https://github.com/osCommerce/oscommerce

# Proposal
OSCommerce uses a hook file for each base file in each language installed.

The hook file defines the translation following the model and is located at *\root\includes\languages\LANGUAGE_NAME\*: 

__define('TABLE_FIELD', 'Table Filed Name in target Language');__

In each base file it uses the following include that points to the specific language file related to the base file:

__require(DIR_WS_LANGUAGES . $language . '/' . FILENAME_ACCOUNT);__
  
Wherever the field in the PHP outpout is used, it uses the following php echo (found at same path as AppGini at *\root\*):

__<?php echo TABLE_FIELD; ?>__

This requires certainly a file structure where all __table names__ and field names are defined, named __database_tables.php__, in a specific file at *\root\includes\*:

__// define the database table names used in the project
  define('TABLE_NAME', 'table_name_in_target_language');__
  
  
Further it requires  a file structure where all __file names__ are defined in a specific file, __named filenames.php__, at *\root\includes\*:  
  
  
__// define the filenames used in the project
  define('FILENAME_ACCOUNT', 'account.php');__


