jquerymobile_problems - PROBLEM CLOSED
=====================

I could not find a way to disable the hash maniuplation, so I have removed jquery.mobile from the project and replaced it with other plugins.

=======================================================================================
I have included jquery mobile in a large project, but didn't realize at the time that it does not support passing information via the hash. I'm committed at this point and am using other functionality of the platform. However, I need to be able to use the hash to implement bookmarks normally as 1) links to a place on the same page 2) links to a place on a different page.

After some research here at github (jquery/jquery-mobile#5465) and in the jquery documentation (http://api.jquerymobile.com/global-config/) it seems like setting the following options on mobileinit should handle this

$.mobile.ajaxEnabled = false;
$.mobile.hashListeningEnabled = false;
$.mobile.pushStateEnabled = false;
$.mobile.changePage.defaults.changeHash = false;

I want links to be treated as ordinary http events and would like to disable jquery's handling of hash, so that it will be handled normally by the browser.

I can't get this to work for either type of bookmarked link
1) links to a place on the same page : link is not clickable at all. if i manually add rel="_external" or data-ajax ="false" to the tag, the same page link will work. but i'd rather handle this globally.
2) links to a place on a different page: the link will jump to the destination page, but does not honor the bookmark location (always loads to top of page). i cannot get this to work at all.

I have added a sample project that demonstrates the issues I'm having in this repo: https://github.com/itrickski/jquerymobile_problems

Any help is greatly appreciated.
