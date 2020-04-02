# online-programs-calendar
A statewide calendar of online events hosted by public libraries from around Ohio during the COVID-19 pandemic.

## Background
In the midst of the COVID-19 pandemic and the extended closure of all of Ohio’s public library buildings, staff at the State Library of Ohio noticed that many libraries across the state were continuing to offer programs to their patrons electronically. Online programs are available to anyone, no matter where they live, but many people are only aware of the programs being put on by their local library. In an effort to make it possible for people to find these programs in one place, the State Library developed this calendar which includes time and date of these online programs as well as where they can be viewed online. All events are submitted by the hosting libraries.

## Tools Used
The calendar is self-contained and does not rely on PHP, SQL, etc. It's built using the following tools:

- [Bootstrap 4](https://getbootstrap.com/docs/4.0/getting-started/introduction/) primarily for the [modals](https://getbootstrap.com/docs/4.0/components/modal/) (i.e. event details)
- [jQuery](https://jquery.com/)
- [FullCalendar.io](https://fullcalendar.io/docs) library using the [List View](https://fullcalendar.io/docs/list-view)

## Event Entries
Events are described in a JavaScript [Event Object](https://fullcalendar.io/docs/event-object) in FullCalendar. The standard fields include the title, start time, and end time, so we must use `extendedProps` to include custom details, such as audience, library name, etc. An example object looks like this:
```
{
  title: 'Online Book Club',
  start: '2020-03-31T16:00:00',
  end: '2020-03-31T17:30:00',
  extendedProps: {
	  library: 'State Library of Ohio',
	  description: 'Join us for an online book club discussion.',
	  audience: 'Adults',
	  link: 'https://library.ohio.gov/'
  }
}
```
Since this is JavaScript, be careful to escape any single quotes in these values, especially the description.
