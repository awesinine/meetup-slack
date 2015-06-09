# meetup-slack
Learn to Code LA's Meetup and Slack Integration

This is a fun little python experiment I'm building out while I learn to code.

meetup-slack is a library that connects slack and meetup through their respective api's to do meetup announcements in slack.

###The main features are:
point to a meetup group using an API
point to a slack group with webhooks enabled via the API

The meetup events will then be announced in slack over some interval
15 mins before the meetup starts, a unique chat room will be spun up and announced in #general
periodically based off of some activity threshold in the active spun up chat room, something interesting will "leak" into #general to let people know where the party is :-D

24 hours after the event closes, the room will be archived and stored in some location (likely our website).

####The second iteration will improve the announcement queuing method to take into consideration peak times when people are active in slack.

messages will be formatted pretty and include easy links with emojiis that display things like available slots and location (clicking will make a call to the google maps api and chart a person from their current location)

The overall idea will be to minimize the need to even bother going through meetup, BECAUSE WHY WHEN WE CAN SLACK?!?!?!?!?


##config.conf
config.conf is a config file that holds all of the api calls / information.  It's a simple dictionary in the following format:

...
{
	'slack_webhook_qa': 'webhook for slack room',
        'slack_webhook_dev': 'webhook for slack room',
        'meetup_api': 'api call for meetup',
        'google_api': 'api call for google maps'
}
...


*note that meetup_api is actually : https://secure.meetup.com/meetup_api/console/?path=/2/events
