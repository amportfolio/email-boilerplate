# Email Boilerplate 1.0

This is a fully responsive boilerplate I use to develop HTML emails. Included is an html file with email-friendly responsive modules all laid out, but easily editable for your needs. Included images are purely for placement purposes and are not to be used to commercial purposes.

## Getting Set Up

If you look at the code, you'll see all the modules are separated with comments. Simply take out the modules you do not wish to use, and style the ones you want to use. When modifying modules, it is advised you stick to using HTML tables and any HTML 4.01 compliant tags you can use. This will ensure your layout will work on most email clients.

In the head area of the file are a set of CSS classes. The first part is a setup to potntially use a web font in the email:

    /*Calling our web font*/
    @font-face {
    	font-family: 'Open Sans';
    	font-style: normal;
    	font-weight: 400;
    	src: local('Open Sans Regular'), local('OpenSans-Regular'), url(https://fonts.gstatic.com/s/opensans/v16/mem8YaGs126MiZpBA-UFVZ0b.woff2) format('woff2');
    	unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
    	mso-font-alt: 'Arial';
    }

This is **NOT** guaranteed to work in every email client, but it can in some. It will need a direct URL though to the font. If you're pulling from Google Fonts, you'll need to do a special trick to get the direct URL to the font, as Google's normal URLs link you to a full set of file versions for the font. This will work in a normal web page, but not an email

So here's what you do:

1. Visit Google Fonts and pick the font you want. Add it to the "cart" you would place a font in for use.
2. Copy just the URL (href) from the link or import code they give.
3. Paste the URL into the address bar of a browser and press Enter. You should see a set of CSS codes for the font
4. Take the source code from "latin" and place it into your boilerplate head
5. Set up a backup font in the line "mso-font-alt" for Outlook, as the web font will not work there.

Be sure to test your email to make sure the web font works on platforms that will allow it. It would also be ideal to select a font that is similar to a web safe font so you do not have a drastically-changing layout.

After the web font, the next grouping of classes are resets and issue fixes crafted by Alex Ilhan. I would strongly advise not to remove these.

    /* Some resets and issue fixes found by Alex Ilhan */
    #outlook a { padding:0; }
    body{ width:100% !important; -webkit-text; size-adjust:100%; -ms-text-size-adjust:100%; margin:0; padding:0; }
    .ReadMsgBody { width: 100%; }
    .ExternalClass {width:100%;}
    .backgroundTable {margin:0 auto; padding:0; width:100%;!important;}
    table td {border-collapse: collapse;}
    .ExternalClass * {line-height: 115%;}
    /* End reset */

The second set of classes are specifically ideal for building the responsive elements of the email. These two allow for the columns to shift in conjunction with the border-collapse setting put on all the table cells. It's up to you which one you wish you use:

    /* One methodology for mobile columns */
    *[class="mobileColBlock"] {display: block;}
     
    /* Another methodology for mobile columns */
    *[class="mobileColFloat"] {float: none !important;width: 100% !important;}

This allows you to hide elements when you go to mobile. You'll see them in use on the headers that contain navigation:

    /* This will hide items when going to mobile */
    *[class="hidden"] {display:none !important;}

You will also need to use this on the cells that remain in the row so they resize to full width when you go mobile:

    /* Sets width to 100% and adjusts height accordingly */
    *[class="fullWidth"] {width:100% !important; height:auto !important;}

You can also use this on images and other items you need to go to full width. You can also center items with CSS if you cannot use table cell centering:

    /* Centers content on mobile */
    *[class="centered"] {text-align:center !important; width:span>100% !important; height:auto !important;}

The rest of the included classes are more for additional padding or more strategic padding. Bear in mind these will only show up on mobile.

## Included Modules

Here's a rundown of the modules in this boilerplate:

* Header with Logo centered
* Header with Logo aligned left
* Header with Logo centered and navigation below. The navigation will vanish on mobile.
* Header with Logo aligned left and navigation aligned right. The navigation will vanish on mobile.
* Main Hero Marquee with background image
* Main Hero Marquee with solid color
* Image-based main Hero Marquee
* Secondary section with four icons (or images) with copy below each
* Secondary section with a basic copy block
* Secondary section with two images and copy below each
* Simple call-to-action text block
* Footer navigation
* Legal section with simple copyright
* Legal section with a block of copy
* More modules will be added as the need arises.

## Questions? Comments? Suggestions?

Please feel free to reach out or fork this and improve on it.

## Authors

* **Alex Moschopoulos** - *Initial work* - [amportfolio](https://github.com/amportfolio)

## Acknowledgments

* Alex Ilhan...for the tweaks and resets, as well as teaching me much.
* [Pexels](https://www.pexels.com/)...for the stock photos.