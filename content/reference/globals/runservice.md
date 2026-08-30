---
title: RunService
description: Service in charge of dealing with properties of the game running
---

## SIGNALS

.Heartbeat:Connect(function(DeltaTime:int)end)
---
the heartbeat signal is fired every tick after the physics simulation has been ran
