---
title: task
description: class related with thread management
---

## METHODS

.wait(Delay:int)
---
Pauses the thread it is called for the duration of time specified by the Delay value

.defer(func:Function)
---
Schedules a new task to be created/resumed at the end of the tick

.spawn(func:Function)
---
Creates/Resumes a new task instantly from the moment it is called

.delay(Delay:int,func:function)
---
Schedules a new task to run on the end of the first tick after the delay has passed
