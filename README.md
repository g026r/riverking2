# Legend of the River King 2 (Rumble Restoration)

## What This Is

When _Kawa no Nushi Tsuri 4_ was released in Japan, it came in a large yellow cartridge with rumble support.

<img width="300" height="418" alt="Kawa no Nushi Tsuri 4" src="https://github.com/user-attachments/assets/09263e67-aa79-460e-9698-8ce4e9e4ddc9" />

When it was localised for international markets as _Legend of the River King 2_, it lost something in the process:

<img width="300" alt="Legend of the River King 2" src="https://github.com/user-attachments/assets/d1ac357d-8d9c-47ed-962d-5c62cfdb4fda" />

But, though the rumble hardware for it wasn't included, the code for it was still there. If the game code was played on a third-party system that supported rumble, then that system would rumble — as long as the system was aware that it _should_ rumble.

## How to Do That?

Download the .bps file from the releases. Apply it to a copy of the game using your favourite patcher. Play & hopefully enjoy.

### I Don't Know How to Patch. Can You Give Me the ROM?

No.

### I Did The Above And Game Doesn't Rumble

If you're playing it on the Analogue Pocket using a DS Rumble Pak, you have to use the spiritualized core. The budude2 core doesn't support rumble at this time.

If you're playing it on another system or via a flashcart, then I dunno.

### I Did The Above, But How Do I Toggle Off the Rumble?

That's the best part: you can't! The code to actually trigger the rumble was left in the game, but the menu item to toggle it on & off was removed. And why would not? The game was released without the hardware for it.

<img height="320" alt="Kawa no Nushi Tsuri 4 menu showing a third rumble option" src="https://github.com/user-attachments/assets/2f6442c8-4680-4b98-9b61-c547fd177577" /> <img height="320" alt="Legend of the River King 2 2025-08-05 21 40 56" src="https://github.com/user-attachments/assets/814fd8b8-665d-487a-9f4c-ea20aa220278" />

Probably someone could patch it back in. But this patch is just a very quick fix to get it working on hardware that follows the stricter Nintendo-style start-up sequence.

## What Does It Do?

In essence, Legend of the River King 2 still supports rumble. But [the cartridge header,](https://gbdev.io/pandocs/The_Cartridge_Header.html) which tells various aftermarket systems what hardware is on the cartridge, doesn't identifiy it as supporting rumble. This patch changes two bytes in the header so that it now reports itself as supporting rumble.

### Two Bytes? But the Patch on Romhacking Only Changes One

Yes, but the patch on romhacking is broken. In addition to changing the cartridge type byte, you also have to change the header checksum byte. If you fail to do that, then anything that follows [the Game Boy boot sequence](https://gbdev.io/pandocs/Power_Up_Sequence.html) will not load the game.

While some aftermarket & third-party systems don't care about the header checksum, others do. By fixing this, it makes the final result usable on as many systems as possible.
