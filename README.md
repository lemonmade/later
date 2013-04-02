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