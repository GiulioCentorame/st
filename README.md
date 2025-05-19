# Patched version of simple terminal (`st`)

Personal version of [`st`](https://st.suckless.org/), currently tracking with `master`'s `0.9.2`. All the patches and customisations are found in the `patched` branch.

## Official patches included

- scrollback (no ringbuffer) + reflow + mouse + altscreen + increment: I opted for this setup over no scrollback + `tmux` as I often open throwaway terminal sessions and I don't necessarily want them to stick around with `tmux`. No ringbuffer is uniquely because reflow doesn't apply cleanly on the ringbuffer variant.
- alpha
- ligatures
- anysize
- bold is not bright
- clickurl (nocontrol)
- delkey
- desktopentry
- externalpipe + eternal + signal
- font2
- xresources with reload signal: I like to keep theming and configuration separate, so I am offloading all the theming and configuration to my dotfiles.

Most patches applied cleanly with `patch --merge -i [file]`, with relatively minor edits. Commits in the `patched` branch list the link for each original patch in the description.

## Custom features

- `st_tmux.desktop`: runs `st -e tmux` when launched. My workflow uses `dmenu` to search for `.desktop` files, so having another `.desktop` file to launch multiplexed sessions comes in handy
