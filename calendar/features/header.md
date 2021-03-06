---
title: Header
page_title: Header | UI for WinForms Documentation
description: Header
slug: winforms/calendar/customizing-appearance/header
tags: header
published: True
position: 0
previous_url: calendar-customizing-appearance-header, /calendar/customizing-appearance/header
---

# Header

The Header area of __RadCalendar__ is located above the calendar's content area. The header contains the calendar title and the navigation buttons.

![calendar-customizing-appearance-header 001](images/calendar-customizing-appearance-header001.png)

Use the the following properties to modify title appearance and functionality:

*  __TitleFormat__ - gets or sets the format string that is applied to the calendar title. 


*  __TitleAlign__ - gets or sets the horizontal alignment of calendar's title.


*  __ShowHeader__ - gets or sets whether the calendar will display the title. 


*  __ShowNavigationButtons__ - gets or sets whether the navigation buttons should be visible.


*  __ShowFastNavigationButtons__ - gets or sets whether the fast navigation buttons should be visible.


*  __FastNavigationNextImage__ - gets or sets the image that is displayed for the fast next navigation control.


*  __FastNavigationNextText__ - gets or sets the text that is displayed for the fast next navigation control. 


* __FastNavigationNextToolTip__ - gets or sets the tool tip that is displayed for the fast next navigation control. 


* __FastNavigationPrevImage__ - gets or sets the image that is displayed for the fast previous navigation control. 


* __FastNavigationPrevText__ - gets or sets the text that is displayed for the fast previous navigation control. 


* __FastNavigationPrevToolTip__ - gets or sets the tool tip that is displayed for the fast previous navigation control. 


* __NavigationNextImage__ - gets or sets the image that is displayed for the navigation next  control. 


* __NavigationNextText__ - gets or sets the text that is displayed for the navigation  next  control. 


* __NavigationNextToolTip__ - gets or sets the tool tip that is displayed for the navigation next  control. 


* __NavigationPrevImage__ - gets or sets the image that is displayed for the navigation previous control. 


* __NavigationPrevText__ - gets or sets the text that is displayed for the navigation previous rev control. 


* __NavigationPrevToolTip__ - gets or sets the tool tip that is displayed for the navigation previous control. 


* __FastNavigationStep__ - gets or sets the number of views that will be scrolled when the user clicks on a fast navigation link.

## Title Properties

You can customize the __RadCalendar Title__ to define how and what information should be shown: 

* Control title alignment using the __TitleAlign__ property. 


* Control title format using the __TitleFormat__ property. For details about available format characters see the [Date Format Pattern]({%slug winforms/calendar/localization/date-format-pattern%}) topic.


* The separator string that is placed between the start and end dates in a MultiView title is controlled by the __DateRangeSeparator__ property. 


* To allow navigation in the calendar, set the __EnableNavigation__ property to true. Customize the fast navigation buttons using the following properties:
     
    - FastNavigationNextImage

    - FastNavigationNextText

    - FastNavigationNextToolTip

    - FastNavigationPrevImage

    - FastNavigationPrevText

    - FastNavigationPrevToolTip

## See Also

* [Column and Row Headers]({%slug winforms/calendar/customizing-behavior/column-and-row-headers%})
* [Footer]({%slug winforms/calendar/customizing-appearance/footer%})
* [Keyboard Navigation]({%slug  winforms/calendar/customizing-behavior/keyboard-navigation%})
* [MultiView]({%slug winforms/calendar/customizing-behavior/multiview-mode%})
* [Navigation]({%slug winforms/calendar/customizing-behavior/customizing-navigation%})
* [Repeating Events]({%slug winforms/calendar/customizing-behavior/repeating-events%})
* [Selecting Dates]({%slug winforms/calendar/customizing-behavior/selecting-dates%})
* [Zoom]({%slug winforms/calendar/customizing-appearance/zooming%})
