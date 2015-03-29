GLOBAL REDIRECT
===============

WHAT?
-----

GlobalRedirect is a simple module which…

- Checks the current URL for an alias and does a 301 redirect to it if it is not being used.
- Checks the current URL for a trailing slash, removes it if present and repeats check 1 with the new request.
- Checks if the current URL is the same as the site_frontpage and redirects to the frontpage if there is a match.
- Checks if the Clean URLs feature is enabled and then checks the current URL is being accessed using the clean method rather than the 'unclean' method.
- Checks access to the URL. If the user does not have access to the path, then no redirects are done. This helps avoid exposing private aliased node's.
- Make sure the case of the URL being accessed is the same as the one set by the author/administrator. For example, if you set the alias "articles/cake-making" to node/123, then the user can access the alias with any combination of case.
- Most of the above options are configurable in the settings page. In Backdrop 5 you can access this after enabling the globalredirect_admin module.

WHY?
----

Once enabled, an alias provides a nice clean URL for a path on a site. However Backdrop does not remove the old path (eg node/1234). The problem is that you now have two URLs representing the same content. This is dangerous territory for duplicate pages which can get you sandboxed by the search engines!

HOW?
----

This module uses hook_init to interrupt the page load and action the alias lookups. If any of the above rules apply then the appropriate action is taken. If no rules apply then the page load continues uninterrupted. An example of this in use is on the site it was developed for. http://www.sportbusiness.com/node/160559 will redirect to http://www.sportbusiness.com/news/160559/lagardere-sets-up-sports-division due to the alias setup on this site.

LICENSE
---------------    

This project is GPL v2 software. See the LICENSE.txt file in this directory 
for complete text.

CURRENT MAINTAINERS
---------------    

Looking for maintainers
Ported to Backdrop by docwilmot (https://github.com/docwilmot)

CREDITS   
--------------- 

This module is a fork of the Backdrop version maintained on Backdrop by Nicholas Thompson 
(https://www.drupal.org/u/nicholasthompson)
