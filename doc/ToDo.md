# The following tasks need to be completed before this app is broadly exposed:

## Lesson Creation
* [x] Generate a list of lessons for the "Pick a Lesson" button by reading all of the ./res/#-content.json files.
* [x] Generate complete cards that include the Lesson number, and the generated list from the lesson picker
* [x] Create an npm command to generate lessons so they don't get generated each time the server restarts
* [ ] Complete Readme that describes how to generate lesson content
* [x] Build a class for lesson specific Action.Submit buttons
* [x] Create links for Show Source based on an environment variable

## Controlled rollout
* [x]  Add logic to be "inoperative" if the space isn't populated by a set of known users when bot is spawaned
* [x]  Change operate/inoperative status when memberships change
* [x] Exit group spaces when a non EFT user added us regardless of other members  
* [x]  Add a persistent store for information about the bots
  * [x]  Store operative/inopareative status
  * [x]  Store current lesson

## Core functionality
* [x]  Add logic to know the most recent card presented.  Respond to submit actions from other cards with a reply that only the most current card's input is processed.
* [x]  Set the threading-api feature toggle for this bot
* [ ]  Add a "syllabus" command, that lays out the lessons in text format and allows the user to specify the leson they want

## Metrics and Feedback
* [x] Add logic for a lesson-feedback.json as the last lesson
* [ ] Write the following "metrics" data
  * [x] Bot Added/Removed from Space
  * [x] Action.Submit button pressed
  * [x] Command entered
  * [x] Feedback Provided
  * [ ] Figure out how to best index this data so that we can run queries such as:
  * [ ] How many spaces is our bot in
  * [ ] How many users have interacted with our bot (ever, this week)
  * [ ] How many users got to the graduation card
  * [ ] How many users interacted with more than X lessons
* [x] Write Add/Remove feedback to a space.  Perhaps create an AdminRoomId instead of AdminEmail for group control
* [ ] Prevous and Current lesson indexes don't always seem to be correct when using text commands, debug
* [ ] Is lessonsSeen counter getting updated in all circumstances?  Seems low in some cases

## Lesson Content
* [x] Show an Input Form
* [x] Handling Attachments
* [ ] Best Practices for when a card is "expired"

## Persistent store
Create a new module for storing config data to a DB
Try to use existing memory store conventions, but reads should not be async.
Research mongo to see if its better to update a single field in a dictionary or 
* [x] on spawn get storeConfig from database and attach to bot
* [x] on bot.store, write to local copy, lazy return from database write with error messages for DB write fails
* [x] on bot.recall read syncronously from local copy
* [x] on bot.forget, update db lazily
* [x] switch over to framework suported persistent store
* [ ] Write some one-time-only code to move from storage v1 to storage v2
* [ ] Add "announce" logic so that bots added to 1-1 spaces during the EFT announce that they are working 1 TIME ONLY!
  

## Framework improvements
* [ ] reimplment beta-mode as a core frameowrk feature
* [x] reimplement mongoStore as a framework store


## Ask Buttons and Cards School
* [x] Create an Ask Buttons and Cards School Space
* [x] Make avaialble with EURL for Cisco only
* [x] Add link to Ask space in More Resources
* [ ] Ask EURL to make link publically avaialble after GA