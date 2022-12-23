---
title: Info
layout: page
permalink: /info
---

{%- assign utils = true -%}
{%- assign lootboxes = true -%}
{%- assign puppeteer = false -%}
{%- for mod in site.data.modlist -%}
    {%- case mod.name -%}
        {%- when 'ToolkitUtils' %}
            {%- assign utils = true -%}
        {%- when 'ToolkitUtils - Testing' -%}
            {%- assign utils = true -%}
        {%- when 'Puppeteer' -%}
            {%- assign puppeteer = true -%}
        {%- when 'TwitchToolkit - Lootboxes' -%}
            {%- assign lootboxes = true -%}
    {%- endcase -%}
{%- endfor -%}


{%- assign bal = '!bal' -%}
{%- assign buy = '!buy' -%}
{%- for command in site.data.commands -%}
    {%- if command.data.isBal -%}
        {%- assign bal = command.usage -%}
        {%- continue -%}
    {%- endif -%}

    {%- if command.data.isBuy -%}
        {%- assign buy = command.usage -%}
        {%- continue -%}
    {%- endif -%}
{%- endfor -%}

# Welcome to the GeckoShop

These instructions go with my stream at [twitch.tv/brassgecko](twitch.tv/brassgecko) and explain how to use 
[Twitch Toolkit](https://steamcommunity.com/sharedfiles/filedetails/?id=1718525787) in order to help or harm 
the colony. If anything's confusing, wrong, or broken please say so in the chat!

NOTE: If the current colony is a very limited toolkit setup, such as for a survival scenario,
items and events may be limited or restricted entirely and the info below may not apply.

## What does Twitch Toolkit do?

Toolkit lets you get your grubby fingers into the colony's business. [Commands]({{- "/commands" | relative_url -}}) are
the ways you can use toolkit. The [store]({{- "/" | relative_url -}}) is your list of all items or events available,
their prices, and any karma effects (see the Karma section below!). Send a pawn to join the chaos and customize
their traits and gear, send resources to help build, send raiders to try to burn everything..

Some useful shortcuts if you have purchased a colonist, to save time and avoid me becoming confused:
- `$wear itemName` to instantly wear armor or clothing
- `$equip itemName` to instantly equip a weapon
- `$wear tribalwear[cloth,normal]`: use [] to specify material and/or item quality
- `$use itemName` to instantly use food (might not fill hunger) or other consumables 
- `$backpack itemName` to put things in your colonist inventory
- `$surgery itemName` to buy a body mod and queue the operation

## What Are Coins?

Coins are the mod's currency, earned each minute while watching. You can view your balance by using the `{{ bal }}` command. 

{%- if lootboxes == true -%}
My bot will also pester you about lootboxes. Check if you have one by typing `!lootboxes` and open
one with `!openlootbox`
{%- endif -%}


<br/>
## What is Karma?

Karma is multiplier on the number of coins you earn - higher karma, more coins! Beneficial events 
will raise your karma, harmful events will lower it, and anything neutral -may- raise your karma, 
depending on the current scenario. Max and min karma may change, or be locked to 100%.

{%- if puppeteer -%}
<br/>
## What is Puppeteer?

[Puppeteer](https://steamcommunity.com/sharedfiles/filedetails/?id=2057192142) is a mod by Brrainz that
allows viewers to directly control their pawns, and even view a number of information about your pawn in
a graphical way. It also redirects some of the responses from Twitch Toolkit to its website to clean up
chat a bit. So, if you're logged into Puppeeter and you're wondering why the bot isn't responding to you,
you should check the `TT` tab on the website first.
{%- endif -%}
