# The Hush House

A co-op horror game for 1–6 players. It's one self-contained page (`index.html`), so there's no build step.

## Deploy to Vercel

Option A, the command line:

    npm i -g vercel
    cd hush-house-vercel
    vercel --prod

Option B, GitHub: push this folder to a new repository, then go to vercel.com/new, import it,
and leave every setting at its default ("Other" framework, no build command).

## How multiplayer works here

Every player sends and receives room updates through two free public relay servers at once
(broker.emqx.io and broker.hivemq.com), so friends on any network can play together and
there's no single "hub" player. If the host leaves, the next player takes over automatically.

Hosts can tick "List this room publicly" in the lobby; public rooms show up under
"Open rooms you can join" on everyone's title screen.

Progress (the level a room has reached, plus each player's coins, items and battery) is
saved in each player's browser, keyed by the room code.
