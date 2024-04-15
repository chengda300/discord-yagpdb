# What is this?
Custom Commands built using "Yet Another General Purpose Discord Bot" (YAGPDB).

# What is "flexible slowmode"?
It allows **X messages** to be sent **every set interval** and it is counted **per channel** (X is more than 1).

## What does it do?
- Discord currently has an in-built slowmode, which allows **exactly 1 message** to be sent **every set interval** and it is counted **per channel**.
- Other public bots handles it by allowing **X messages** to be sent **every set interval** but it is counted **per server**
  - This means, **all channels will count to the same limit**, which is not suitable for the server I manage since it has **about 40 channels**.
With this custom command, it uses YAGPDB's database to store the usage count and also checks if a set amount of time has elapsed.

## Benefits
- Allows what other bots have implemented for slowmode but **counting per channel**.
- Allows **flexible slowmode cooldown depending on user type**.
  - In this example code, Server Boosters get an additional benefit of 1 additional count (X is increased by 1 compared to other users) and 15% reduced slowmode cooldown.
  - Also in this example code, depending on the tier of the user in the server, the slowmode cooldown reduces further by up to 20%.
  - When using this example code, please change the ID of the roles to match the ones on your server.

## Downsides
- YAGPDB's database has an upper limit of **50 entries multiplied by user count in server**. If each user has an entry for each channel and the server has 50 channels, the database will be full.
- Some servers may also use the database for other purposes, so the practical limit is even lower for this slowmode feature.

# What is "pin message at bottom"?
It is to **force the most recent message to be a set message** and **without clutter**.

## What does it do?
- Sends the desired message when someone else sends another message, and deletes the previous instance of the desired message sent earlier.
- Unlike reminder bots running at high frequency, this custom command will **delete the previous instance**.
  - However, 1 entry in the database will be used for this per channel that uses this.
 
## Benefits
- Better visibility for 1 pinned post (because Discord hides pinned posts so well it might as well not be pinned)
- Reduced clutter compared to reminder bots running at high frequency (only 1 instance of the message exists per channel)

## Downsides
- It takes up 1 entry per channel in YAGPDB's database.
