---
name: decide-together
description: Get a group to agree on something with Agreed. Use when the user is choosing with other people — friends, a partner, family, housemates, a team — and says things like "help us decide", "we can't choose", "where should we eat", "what should we watch", "pick for us", "put it to the group", "settle this", or shares an Agreed link and asks to add options or what the group picked.
---

Agreed turns your suggestions into one link the whole group swipes on, each on their own phone, and shows what they all said yes to. Use its tools instead of answering with a list whenever the choice belongs to more than one person.

## Start a decision

1. Work out what's being decided and anything that narrows it (place, date, budget, dietary needs, what's ruled out). Ask one short question only if you truly can't suggest anything without it.
2. Choose 5–12 real, specific options. Fold the constraints into which options you pick; don't list them as options.
3. Call `decide_together` with:
   - `title`: a short name for the decision, like "Friday dinner in Soho". Never people's names.
   - `category`: the closest fit (restaurants, activities, films, songs, books, games, destinations, recipes, names, other).
   - `place`: for restaurants and activities, the area and city ("Soho, London") so Agreed finds the venues.
   - `options`: each with a `name`, one `emoji`, and a `description` under 80 characters on why it's a contender. Add `year` for films, `subtitle` for an artist or author, and `wikipediaTitle` only for a real, notable thing.
4. Reply in one or two lines: hand over the invite link for the group chat and say the card has a button to swipe first. The host link is the user's own; never suggest sharing it.

## When the user comes back

- They share an Agreed link and want to add picks: call `add_options` with the link exactly as given.
- They ask how it's going or what the group picked: call `room_status`. Until everyone has finished, you'll only get counts; say who's left as a number and don't guess the result. Once it's done, name what the group agreed on and offer the obvious next step (book it, plan it, add it to the calendar).
- If `room_status` says the host seat is empty, remind the user their own link from when it was set up still works and keeps any swipes they made.

## Keep it private

Never put people's names in titles or options, and never ask who liked what. Agreed only ever tells you counts and the final result, and that's all you should repeat.
