# Later.scpt
## by Chris Sauvé of [pxldot](http://pxldot.com)


## Description
This script allows you to defer all selected OmniFocus items by a certain amount of time/ to a particular date and time. You can defer the start or due dates, depending on your preferences. The script can also automatically flag all deferred tasks.


## Syntax
The script will prompt you to enter the amount of time you wish to defer the selected items by. You can use relative dates, absolute dates, and times in 12- or 24-hour format when deferring the tasks. The available options are as follows:

- **Relative date**: Deferring the task by a given amount of weeks and days, using `weeks` or `w` to denote weeks and `days` or `d` to denote days. For example, `2w 1d` and `2 weeks 1 day` both defer the items by 15 days from their existing start/ due dates.

- **Absolute date**: You can specify an absolute date using the month and day of the month desired, using either short- or long-form to denote the month. For example, `jan 21` and `January 21` will both defer the items to the next January 21.

- **Absolute date using preferred short-form date format**: You can also specify an absolute date using the order for day, month and year that you have specified in the Languages & Text Preference Pane. For example, if your short-date format is specified as YY/MM/DD, you can use this same format to specify the date of the selected items (i.e., `14/01/01` will defer the items to January 1, 2014). You can exclude the year and the script will still understand what you mean, and will select this year if the date has yet to pass or next year if it has (i.e., if your short-date format is in YY/MM/DD, `01/01` will still defer the items to January 1, 2014 if you are in the year 2013, after January 1, 2013). You can only use `.`, `-` or `/` to delimit day/ month/ year in the short date format for this to work.

- **Time**: You can specify a particular time using 12-hour (i.e., `2:00PM`, `2p`, `2:30a` or `230AM`) or 24-hour (i.e., `14:00`, `1400`, `2:00` or `230`) time formats. If no time is specified, the script will default to midnight of the specified date.

You can combine any of the date formats with any of the time formats. If you exclude a date specification, the script will default to selecting the next occurance of the given time (i.e., specifying `2:30PM` will set the time to 2:30PM today if you run the script before 2:30PM, or 2:30PM tomorrow if you have already passed it).


## Runtime Options
- The script will ask you whether you would like it to automatically flag all items you run the script on. This can be changed at compile-time by editing the `usesFlagsForScheduling` property.

- The script will prompt you to select whether you use start or due dates for scheduling, and will only change these dates when defering items. You can change this default at compil-time by editing the `methodForScheduling` property. You can also override the default on a case-by-case basis by writing `due` or `start` before the date/ time to which you are deferring the items (i.e., `due 2d 2PM` will defer the due date of all selected items to two days from now at 2PM). You can also defer both start and due dates simultaneously by including both with their desired deferrals. (i.e., `start 2d due 5d 2pm`).


## Installation
Download the most recent version of the script. Once you have downloaded the script, navigate to your Application script folder located at `~/Library/Scripts/Applications/OmniFocus`. Apple hides the Library folder in Mac OS X 10.7 or later by default, so the easiest way to get to this folder is to select the menu item `Go > Go To Folder...` in Finder.app. You may have to manually create an OmniFocus folder in the `~/Library/Scripts/Applications` directory if you do not have any previous scripts for OmniFocus (you may have to create more of the folders in the directory; if you don't have an Applications folder or even a Scripts folder, you will have to create those as well).


## Using The Script
There are countless ways you can run the script. If you are a pro user, you likely know even more ways than I do: options like launching the script from FastScripts, Alfred, LaunchBar, or a Keyboard Maestro macro are all available to you. Below I'll explain two ways to run the script, primarily targetted at more novice users.

Your first option is to run the script from Apple's AppleScript menu. If you don't have a little script icon near the clock in your Mac's menubar, you need to turn this on manually. Open AppleScript Editor.app from your `Applications > Utilities` folder. Go to AppleScript's preferences by selecting `AppleScript Editor > Preferences...` from the menubar. On the "General" pane, you should check the checkbox to "Show Script menu in menu bar". Now, when in OmniFocus, select the new script menubar item and you will see the script at the bottom of the list, ready to be clicked and run.

OmniFocus has another way to run scripts, and it's even easier than the method described above. Once the script is installed, go to OmniFocus and right- (control-) click on the toolbar (the gray bar at the top of the window that shows icons for your inbox, projects, and more). Choose "Customize Toolbar..." from the contextual menu that pops up. You will then see a list of all items that can be put in your menubar, including (at the bottom) any scripts that you have installed. Drag the script anywhere on the toolbar and click "Done". You now have one-click access to run this script!


## Version History
- **0.3.1** (April 2, 2013): You can now set both the start and due date deferral by typing "start <start deferral> due <due deferral>" (or the other way around)

- **0.3.0** (March 13, 2013): Handles absolute dates in the format you specify in System Preferences as the "short date" format (i.e., 13.04.01 might be April 1, 2013; you can also omit the year, like in 04.01, and combine it with times, like in 04.01 15:00)

- **0.2.4** (February 15, 2013): Better error handling.

- **0.2.3** (January 9, 2013): Added an escape to choose due/ start, regardless of default (just write "due" or "start" at the beginning of your input)

- **0.2.2** (January 7, 2013): Added the option to use due instead of start dates for scheduling

- **0.2.1** (January 6, 2013): Recognizes "tomorrow" as a valid input

- **0.2** (January 1, 2013): You can now use relative (i.e., 5d 4pm), absolute (i.e., January 6 4:00pm), or weekdays (Sunday 16:00) to specify the date and time desired.

- **0.1** (December 29, 2012): Initial release


## License
Use it, change it, repackage it, whatever. Try not to take credit for my work.