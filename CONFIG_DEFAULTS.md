# Pack-default client configs (PROPOSAL)

Source: `docs/client.md` section 3. Each file under `config/` is a copy of the instance's current file with ONLY the
values below changed (everything else is the user's current value, i.e. mostly mod defaults). Not shipped on purpose:
`options.txt`, `servers.dat`, `shaderpacks/` (BSL, Photon, Solas, Miniature stay instance-only), `chunksmith/config.json`
(server keys) and the orphan configs listed in docs/client.md. Rows where current == default value are "pin" rows.
Note: `config/DistantHorizons.toml` still contains the `[server]/[common]` sections of the user's file (not trimmed).
Xaero profile files and Iris properties are rewritten by the mods at runtime; treat them as first-launch defaults.

| file (under `config/`) | key | user's current | pack default | reason |
|---|---|---|---|---|
| `seasonhud-client.toml` | `hud_scale` | `1.0` | `0.8` | smaller, more discreet |
| `xaero/minimap/profiles/default.cfg` | `display_radar` | `true` | `false` | mob radar is game-y; immersion |
| `xaero/world-map/profiles/default.cfg` | `footsteps` | `true` | `false` | footstep trail clutters the map |
| `xaero/world-map/profiles/default.cfg` | `display_minimap_radar` | `true` | `false` | match minimap (radar off) |
| `xaero/world-map/profiles/default.cfg` | `display_opac_claims` | `true` | `false` | no claims system (OPAC) on this server |
| `xaero/world-map/profiles/default.cfg` | `map_teleport_allowed` | `true` | `false` | survival: no teleporting from the map |
| `xmmp.toml` | `checkUpdate` | `true` | `false` | no update nags; the pack controls updates |
| `DistantHorizons.toml` | `lodChunkRenderDistanceRadius` | `512` | `256` | must work on mid-range PCs; players can raise it |
| `DistantHorizons.toml` | `enableSsao` | `true` | `false` | GPU cost, not vanilla-like |
| `DistantHorizons.toml` | `enableAntiAliasing` | `true` | `false` | GPU cost |
| `DistantHorizons.toml` | `enableAutoUpdater` | `true` | `false` | pack controls versions |
| `DistantHorizons.toml` | `showDhOptionsButtonInMinecraftUi` | `true` | `false` | no extra button in pause/options UI |
| `DistantHorizons.toml` | `showHighVanillaRenderDistanceWarning` | `true` | `false` | noisy on first join |
| `DistantHorizons.toml` | `showLowMemoryWarningOnStartup` | `true` | `false` | noisy on first join (revisit if RAM < 6 GB) |
| `sound_physics_remastered/soundphysics.properties` | `environment_evaluation_ray_count` | `32` | `24` | CPU cost with many voicechat players |
| `sound_physics_remastered/soundphysics.properties` | `environment_evaluation_ray_bounces` | `4` | `3` | CPU cost with many voicechat players |
| `lambdynlights.toml` | `light_sources.creeper` | `simple` | `off` | creeper glow gives the monster away; keeps survival tense |
| `jade/jade.json` | `overlay.overlayScale` | `1.0` | `0.8` | smaller overlay |
| `jade/jade.json` | `overlay.alpha` | `0.7` | `0.6` | more transparent |
| `jade/jade.json` | `general.displayMode` | `TOGGLE` | `HOLD` | less persistent HUD |
| `jade/jade.json` | `entity_armor (mob plugin toggle)` | `true` | `false` | keep mob health, hide armor |
| `naturescompass.json` | `client displayWithChatOpen` | `true` | `false` | tidy HUD while chatting |
| `explorerscompass.json` | `client displayWithChatOpen` | `true` | `false` | tidy HUD while chatting |
| `visuality.json` | `slimeEnabled` | `true` | `false` | flashy effects off |
| `visuality.json` | `chargeEnabled` | `true` | `false` | flashy effects off |
| `visuality.json` | `sparkleEnabled` | `true` | `false` | flashy effects off |
| `visuality.json` | `waterCircles.density` | `10` | `6` | subtle ripples |
| `visuality.json` | `waterCircles.radius` | `16` | `12` | subtle ripples |
| `visuality.json` | `hitParticlesEnabled` | `true` | `false` | clutter, not vanilla |
| `visuality.json` | `shinyArmorEnabled` | `true` | `false` | glints off |
| `visuality.json` | `shinyBlocksEnabled` | `true` | `false` | ore ESP-like hints spoil exploration |
| `particlerain/config.json` | `perf.maxParticleAmount` | `1500` | `1000` | cheaper |
| `particlerain/config.json` | `perf.particleDensity` | `75` | `60` | cheaper |
| `controlify/controlify.json` | `global.show_splitscreen_ad` | `true` | `false` | no ads in the UI |
| `controlify/controlify.json` | `global.notify_low_battery` | `true` | `false` | no notices in the UI |
| `iris.properties` | `disableUpdateMessage` | `false` | `true` | no update nags |
| `iris.properties` | `enableShaders` | `false` | `false` | vanilla look by default (unchanged) |
| `iris.properties` | `shaderPack` | `BSL_v10.1.8.zip` | `` | no shader preselected (shaderpacks are not bundled) |
| `sodium-options.json` | `performance.use_no_error_g_l_context` | `true` | `false` | avoid the NO_ERROR_CONTEXT workaround/crash until resolved |
