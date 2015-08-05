---
layout: "blog"
date: "2011-02-25 14:53:00 UTC"
published: true
title: "Production Issues and 3rd Line Support Processes"
author: "Austin Fagan"

---

Another perfect release- this is what it’s all about, now time to kick back, cocktail in hand, bathing in the glorious glow of heaped praise as stakeholder after stakeholder thank Goldilocks and the Three Bears for managing to translate their requirements into flawless, working software. Ok we may have slipped into dreamland there. &nbsp;Here’s what really happened:  
  
 It’s the 35th release and the sales department is deliriously happy. Their sales systems are implemented in an agile fashion so they can stay well ahead of their competitors as they can react quickly to the market. They’ve had a huge increase in customers but unfortunately they’re not all happy ones. Customer services have been inundated with a whole host of complaints. Luckily for them they have a 3rd line support team armed to the teeth with agile weaponry. Now let’s see how they put their agile arsenal to good use.

A number of orders have been reported as delayed. A bit of SQL magic later and it is discovered that hundreds of customers have been affected for one specific product range. Liaising with the development team it is debated whether it is expected behaviour, let’s assume in this instance it is not. An issue tracking ticket needs to be raised. The product range affected is the latest premium range but there are a relatively small number of orders in trouble we’re going to raise it as a major issue- one which does not need immediate attention. The SQL query and any relevant logging information found are attached to the ticket. &nbsp;The issue summary is written on a bug card and goes in the ‘New’ column on the support task board.

There’s a quick discussion on the priority of this issue. Only a small number of customers are affected so it’s not a showstopper that requires an immediate fix in production. It looks likely to be classed as either ‘Critical’, it will be fixed in the next release, or ‘Major’, it will be planned into a later iteration. &nbsp;They decide on ‘Critical’ but will downgrade it to ‘Major’ if there is an easy workaround.

In the meantime there are hundreds of customers with orders in limbo- a workaround needs to be identified. One of the developers pairs with the support person and together they see the workflow wasn’t triggered due to lost messages. So the workaround is to generate these messages and drop them into the system. Great news indeed, now we can update customer services letting them know a bug has been raised and its priority set to ‘Major’ and that the workaround has been applied for all affected orders. We add the workaround to the ticket and the bug card gets a nice blue sticker as it’s a manual workaround but doesn’t require a huge amount of effort.

Next morning at stand-up the bugs raised that previous day are discussed and the cards in the ‘New’ column are moved into ‘In Progress’. After stand-up the team go through the board and people take ownership of the workarounds that need to be played that day.

A call comes through from Sales, they’re very appreciative that the issue raised the previous day has been investigated so quickly and that it is being treated as major. They want to give you flowers. They want to know what time today the fix goes into production. &nbsp;When they hear it’s not even planned to go into production anytime soon and that 'Major' is not a high priority you’re passed on to the Sales Director who takes back the offer of flowers and in return shouts some quite colourful expletives down the phone. As it turns out there’s an advertising campaign set to start the following week and they are hoping for millions of sales of this one product range. Also we really want those flowers so the bug gets raised to the highest priority.

Two weeks later at the retrospective one of the points raised was a support team member getting shouted at by senior management and while the team discuss briefly hiring professional hit-men the action that comes out is to involve the stakeholder in the prioritising of bugs in the first place.

So when the agile support team confirms a production issue their initial analysis will follow a process similar to the following:

- Quantify orders affected
- Liaise with relevant team
- Raise issue-tracking ticket with appropriate priority
- Identify workaround
- Collate logging information

Now the issue has been highlighted and is in the development pipeline support still has work to do, the following steps will be repeated on a regular basis:

- Update business
- Implement work around
- Keep issue visible

Bug cards are kept on the task board with stickers denoting the type of workaround. Without cards to represent the various issues it’s all too easy to lose sight of them and the necessary workarounds won’t happen. &nbsp;Not every issue can be fixed immediately and in the meantime the business can suffer if workarounds are not implemented on a regular basis. Until the issue is fixed in production the bug card should remain on the board. The board enables issue visibility to the team and allows anyone outside the team to get a feel for the current production issues.

Support stand-ups ensure the whole team is aware of current issues. Involved discussion should be avoided otherwise the stand-up could take days! Only the summary of the issue should be mentioned at stand-up and then if anyone has questions on it they can take it offline.


