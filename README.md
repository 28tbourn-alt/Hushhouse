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

On a normal website, players connect peer-to-peer through PeerJS (its free public signaling
server at 0.peerjs.com). The player who creates the room is the hub. If they close the page,
everyone else returns to the title screen and can rejoin with the same code; the first person
back becomes the new hub.

Progress (the level a room has reached, plus each player's coins, items and battery) is
saved in each player's browser, keyed by the room code.
