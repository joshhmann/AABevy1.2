# PlayerBot server migration support

The owner fork is `joshhmann/AABevy1.2`; its initial main client baseline is
`4f8c31bbc76ff777057f20ac6a800abe954e6dbb`. The server migration lives in
[joshhmann/AAEmu-1.2-Rust](https://github.com/joshhmann/AAEmu-1.2-Rust).
Bots remain ordinary server characters. This client should receive their normal
character, movement, equipment, skill and interaction events; no client-side bot
brain is planned.

The initial server checkpoint verifies an authenticated native scripted protocol
client, ordinary character state and a cold Game restart. That is not a Bevy
rendering or human-playability result. Next client acceptance is one player
entering the isolated Rust world and observing a real bot's appearance, movement,
actions and clean departure/reappearance.

The editor's existing engine pin `17d6258a1bca978c61830354b9e9832d08f0eea8`
belongs to the original NickMesser client history, separate from this mainline.
The `compat/editor-engine-17d6258a` branch preserves that exact commit so the
owned editor fork can use its existing engine without a speculative API upgrade.
Do not merge that compatibility branch into main or mistake it for current client
feature work. Align editor/main engine APIs as a separately verified change.

No client gameplay or rendering behavior changes in this fork-setup branch.
