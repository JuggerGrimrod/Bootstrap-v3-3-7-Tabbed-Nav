# Bootstrap 3.3.7 Tabbed Nav Local and Remote v1.0.0 (@ /JuggerGrimrod/Bootstrap-v3-3-7-Tabbed-Nav)

## This Git repository contains markup, script and style assets for a Bootstrap Tabbed Navigation demonstration.

This demonstration is meant to satisfy the requirement of on-page linking to (and activation of) Bootstrap 3.3.7 navigation tabs (.nav .nav-tabs) and tab-panes, and to satisfy a requirement of remote-linking to (and activation of) Bootstrap 3.3.7 navigation tabs (.nav .nav-tabs) and tab-panes.  

The snippets gathered here aren't all unique (some are, some aren't), and one component here originated on a StackOverflow thread concerning remote-linking via hashed URLs.  This demonstration arose from a real-world client request to make all of this stuff happen within the scope of an FAQ page on the client's website.  As with the previous incarnation of this demonstration for Bootstrap 2.3.2, I've assembled everything you see here for the benefit of the developer community as I never found any one resource which addressed all of this demonstration's features and functions in one place.  Additionally, I've updated JS and jQuery functions here to prevent errors caused by migration to the jQuery 3.3.1 library.

This demonstration uses .html pages and Bootstrap v3.3.7 JS/CSS assets.  All Bootstrap JS and CSS files implemented in this demonstration are minified, and are linked in the HEAD of each .html file. This demonstration uses the **/js/jquery.3.3.1.min.js** jQuery library.

The Raleway Font is provided via the Google Fonts API call, linked in the HEAD of each .html file.

* ### /index.html is the content page, and the landing page for inbound links to navigation tabs; this file also contains on-page links to the navigation tabs:
  * The *#navRow* div in **/index.html on lines 84 to 98** contains optional on-page links (*.onPageNav*) which work to show/hide tab-panes and *.active* tab displays farther down-page; these links do not have *data-toggle="tab"* attributes, and their behavior is defined by the *$('.onPageNav').click()* function in **/index.html on lines 33 to 52**.
  * The *.tabbable* div in **/index.html on lines 127 to 133** contains the default instance of Bootstrap tabbed-navigation; these tab links work to show/hide tab-panes and *.active* tab displays.
  * The JS and jQuery scripts in the HEAD of **/index.html on lines 33 to 51** define the on-page linked navigation tab behavior.
    * An additional script defines scrolling behavior in **/index.html on lines 45 to 49**; a *.click()* on an *.onPageNav* link will scroll to the relevant "shown" navigation tab-pane location, with the relevant nav tab *.active* indicator displayed.
  * The JS and jQuery script function *splitURL()* in the HEAD of **/index.html on lines 55 to 72** defines the remotely-linked navigation tab behavior.
    * A callback to the *splitURL()* function handles remote inbound links from **/remote.html** on *window.load* and is defined in **/index.html on lines 70 to 72**.
  * Both the on-page and remotely-linked scripts utilize the JS *.match()* method to detect the presence of a hash symbol appended to the page URL, which is converted to a string variable; if a hash symbol is present in the URL string variable, the JS *.split()* method is employed to strip the hash symbol from the URL string, set the new URL string as a variable, and use the updated URL string to show the appropriate navigation tab via the jQuery *.tab('show')* method.
  * A default display use-case is defined in **/index.html on lines 63 to 66**: if no hash is detected in the URL location string, "tab 1" is set as the active/shown navigation tab.  Commenting this script block out wil result in no tab *.active* indicator or shown navigation tab pane.
  * Console logging is enabled in **/index.html on line 44** to indicate *targetID* for on-page clicks of the *.onPageNav* links.
  * To satisfy features of the jQuery 3.3.1 library, several updates were implemented to teh scripts in **/index.html on lines 44, 46, 61, and on lines 71 to 73**:
    * To prevent *Unrecognized Expression* errors, jQuery 3.3.1 requires special character escaping, which in this instance meant converting instances of '#' to '\\#'' on lines 44, 46 and 61.
    * To prevent *Uncaught TypeError* errors, jQuery 3.3.1 demands a replacement for the deprecated (as of jQWuery 1.8+) *.load)* method; in this case, *$(window).load(function(){* was updated to *$(window).on('load', function(){* on line 71.

* ### /remote.html is the remote-link page, which refers traffic to the Bootstrap navigation tabs on **/index.html**:
  * This page contains links which point to **/index.html** with hashed strings appended to each link (e.g. */index.html#firstTab*).
  * Each link's URL corresponds to Bootstrap navigation tabs on **/index.html** (i.e. */index.html#firstTab*, */index.html#secondTab*, */index.html#thirdTab*).

This Bootstrap 3.3.7 tabbed navigation demonstration was tested from a production Linux server running PHP v5.6.33 in Chrome 63.0.3239.132, Firefox 57.0.4, IE Edge, IE10 and IE9 (emulated via IE Edge console), Windows Safari 5.1.7 (lol...but seriously, this obsolete Safari browser still retains some value as a sort of 'indicator-species': when 'normal' or 'routine' layout and display features fail in Windows Safari, they're likely also fail in iOS Mobile Safari, which is handy for developers who don't have access to a Mac), iOS Mobile Safari via iPad Air 2, and Android Chrome.

### COMMENTS GALORE: Comments appear throughout this demonstration's .html files; if you need to figure out what a given element is doing, chances are very good that there are comments explaining in detail what is going on with each component within each file.

Future enhancements for this demonstration include:

  * Clone of this Github demonstration using **Bootstrap 4.0.x** and the **jQuery 3.3.1 library**.

That's it.  Enjoy!

## Bootstrap 3.3.7 Tabbed Nav Local and Remote README.md file v1.0.0 

### Free to all via GNU General Public License v3.0.
