# Salamander Drumkit — normalized mirror

536 samples from the Salamander Drumkit by Alexander Holm, renamed to one shared naming scheme, with an Opus twin of every sample.

## Why this repository exists

This is a good-will mirror. It makes the Salamander Drumkit easy to fetch in one place and under one naming scheme. It is **not** the author's repository, and the author's own download remains the canonical source. The audio is unchanged; only the file names are normalized, and Opus copies are added alongside the untouched WAVs.

## Licence

**Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)** — <https://creativecommons.org/licenses/by-sa/3.0/>

The upstream README states:

> Licence: CC-by-sa
> http://creativecommons.org/licenses/by-sa/3.0/

The full licence text is in [`LICENSE`](LICENSE).

This mirror is an unmodified-names-only republication: the WAV samples are the upstream bytes, copied and renamed but not resampled, trimmed, normalized or otherwise altered. The files under `opus/` are format conversions of those same samples and are offered under the same CC BY-SA 3.0 licence.

## Credits

- **Alexander Holm** — author. He built the drumkit in 2009 and recorded the samples; the upstream README lists the drums, cymbals and heads used. Contact: `axeldenstore (at) gmail (dot) com`.

No other author or contributor is named by the source.

## Links

- Upstream / original download: <https://archive.org/details/SalamanderDrumkit>
- Licence: <https://creativecommons.org/licenses/by-sa/3.0/>
- Licence text: <https://creativecommons.org/licenses/by-sa/3.0/legalcode>

## What is here

- **Samples:** 536
- **Source payload:** 501910168 bytes (501.91 MB) of WAV under `source/`
- **Opus payload:** 34126917 bytes (34.13 MB) under `opus/`
- **Source format:** 48 kHz, stereo, 24-bit PCM WAV
- **Opus format:** 48 kHz, 160 kbit/s VBR, frame size 20 ms

Every sample has both a `source/` file and a same-stem `opus/` file.

## Naming

```
salamander_<piece>_<articulation>_<perspective>_vl<NN>_rr<N>.<codec>
```

- `perspective` is always `main`: the pack ships a single overhead mic set (the upstream `OH` directory), so there is only one perspective.
- `vl<NN>` is a dynamic-layer index, not a MIDI velocity. `vl01` is the softest layer; layers ascend with loudness.
- `rr<N>` is the source's own take number for that piece, articulation and layer; it is `1` when the source has only one take.
- `take` is absent: the pack has one mic set and no separate front/rear/beater variants.

Pieces used in this pack: `kick1`, `kick2`, `snare1`, `snare2`, `tom1`, `tom2`, `hihat`, `crash1`, `crash2`, `crash3`, `ride1`, `ride2`, `china1`, `china2`, `splash1`, `cowbell1`, `other`.

Articulations used in this pack: `hit`, `mute`, `sidestick`, `closed`, `open`, `foot`, `footsplash`, `tight`, `quarter`, `half`, `loose`, `tip`, `shank`, `edge`, `bell`, `choke`.

### Source tokens and how they were mapped

- The upstream `_OH_` token is a mic label (overhead). All samples come from that one mic set, so it is dropped and the perspective is `main`.
- The upstream dynamics are `P`, `MP`, `F`, `FF`, plus `PP` (floor tom, ride 2) and `Ghost` (the two snares). They are ordered softest first, so `P`/`PP`/`Ghost` land on `vl01` and louder layers follow.
- `snare` → `snare1`; `snare2` → `snare2`.
- `snareOFF` / `snare2OFF` are the snares-off variants of those two drums → articulation `mute`.
- `snareStick` → `snare1`, articulation `sidestick`.
- `hiTom` → `tom1`; `loTom` → `tom2` (ascending size).
- `hihatFoot` → `foot`; `hihatFootStomp` → `footsplash`.
- `hihatSemiOpen1` … `hihatSemiOpen7` are seven distinct pedal-openness positions. They map, in ascending openness, to `tight`, `quarter`, `half`, `loose`, `tip`, `shank`, `edge`.
- `ride1Bell` / `ride2Bell` → articulation `bell`.
- `ride2Crash` → `ride2`, articulation `edge` (a ride struck at the edge as a crash); `ride2CrashChoke` → `ride2`, `choke`.
- `crash1Choke`, `crash2Choke`, `china1Choke`, `china2Choke` → the matching cymbal, articulation `choke`.
- `bellchime` → piece `other`, articulation `bell`.
- `hihatSemiOpen1_OH_P_.wav` has no take number → `rr6` (takes 1–5 already exist for that layer).

Four files are present upstream but not referenced by the shipped SFZ; they are still samples and are mirrored: `cowbell_P_11`, `hihatOpen_OH_FF_6`, `snare_OH_FF_9`, and `hihatSemiOpen1_OH_P_`.

## Mapping table

The same data is in [`MAPPING.csv`](MAPPING.csv), one row per sample, sorted by new name.

<details>
<summary>Full original-to-new table (536 samples)</summary>

| Original (upstream path) | New name |
|---|---|
| `OH/china1Choke_OH_F_1.wav` | `salamander_china1_choke_main_vl01_rr1.wav` |
| `OH/china1_OH_FF_1.wav` | `salamander_china1_hit_main_vl01_rr1.wav` |
| `OH/china1_OH_FF_2.wav` | `salamander_china1_hit_main_vl01_rr2.wav` |
| `OH/china1_OH_FF_3.wav` | `salamander_china1_hit_main_vl01_rr3.wav` |
| `OH/china1_OH_FF_4.wav` | `salamander_china1_hit_main_vl01_rr4.wav` |
| `OH/china1_OH_FF_5.wav` | `salamander_china1_hit_main_vl01_rr5.wav` |
| `OH/china1_OH_FF_6.wav` | `salamander_china1_hit_main_vl01_rr6.wav` |
| `OH/china1_OH_FF_7.wav` | `salamander_china1_hit_main_vl01_rr7.wav` |
| `OH/china1_OH_FF_8.wav` | `salamander_china1_hit_main_vl01_rr8.wav` |
| `OH/china2Choke_OH_F_1.wav` | `salamander_china2_choke_main_vl01_rr1.wav` |
| `OH/china2_OH_FF_1.wav` | `salamander_china2_hit_main_vl01_rr1.wav` |
| `OH/china2_OH_FF_2.wav` | `salamander_china2_hit_main_vl01_rr2.wav` |
| `OH/china2_OH_FF_3.wav` | `salamander_china2_hit_main_vl01_rr3.wav` |
| `OH/china2_OH_FF_4.wav` | `salamander_china2_hit_main_vl01_rr4.wav` |
| `OH/china2_OH_FF_5.wav` | `salamander_china2_hit_main_vl01_rr5.wav` |
| `OH/china2_OH_FF_6.wav` | `salamander_china2_hit_main_vl01_rr6.wav` |
| `OH/cowbell_P_1.wav` | `salamander_cowbell1_hit_main_vl01_rr1.wav` |
| `OH/cowbell_P_10.wav` | `salamander_cowbell1_hit_main_vl01_rr10.wav` |
| `OH/cowbell_P_11.wav` | `salamander_cowbell1_hit_main_vl01_rr11.wav` |
| `OH/cowbell_P_2.wav` | `salamander_cowbell1_hit_main_vl01_rr2.wav` |
| `OH/cowbell_P_3.wav` | `salamander_cowbell1_hit_main_vl01_rr3.wav` |
| `OH/cowbell_P_4.wav` | `salamander_cowbell1_hit_main_vl01_rr4.wav` |
| `OH/cowbell_P_5.wav` | `salamander_cowbell1_hit_main_vl01_rr5.wav` |
| `OH/cowbell_P_6.wav` | `salamander_cowbell1_hit_main_vl01_rr6.wav` |
| `OH/cowbell_P_7.wav` | `salamander_cowbell1_hit_main_vl01_rr7.wav` |
| `OH/cowbell_P_8.wav` | `salamander_cowbell1_hit_main_vl01_rr8.wav` |
| `OH/cowbell_P_9.wav` | `salamander_cowbell1_hit_main_vl01_rr9.wav` |
| `OH/cowbell_MP_1.wav` | `salamander_cowbell1_hit_main_vl02_rr1.wav` |
| `OH/cowbell_MP_2.wav` | `salamander_cowbell1_hit_main_vl02_rr2.wav` |
| `OH/cowbell_MP_3.wav` | `salamander_cowbell1_hit_main_vl02_rr3.wav` |
| `OH/cowbell_MP_4.wav` | `salamander_cowbell1_hit_main_vl02_rr4.wav` |
| `OH/cowbell_MP_5.wav` | `salamander_cowbell1_hit_main_vl02_rr5.wav` |
| `OH/cowbell_MP_6.wav` | `salamander_cowbell1_hit_main_vl02_rr6.wav` |
| `OH/cowbell_MP_7.wav` | `salamander_cowbell1_hit_main_vl02_rr7.wav` |
| `OH/cowbell_MP_8.wav` | `salamander_cowbell1_hit_main_vl02_rr8.wav` |
| `OH/cowbell_MP_9.wav` | `salamander_cowbell1_hit_main_vl02_rr9.wav` |
| `OH/cowbell_FF_1.wav` | `salamander_cowbell1_hit_main_vl03_rr1.wav` |
| `OH/cowbell_FF_2.wav` | `salamander_cowbell1_hit_main_vl03_rr2.wav` |
| `OH/cowbell_FF_3.wav` | `salamander_cowbell1_hit_main_vl03_rr3.wav` |
| `OH/cowbell_FF_4.wav` | `salamander_cowbell1_hit_main_vl03_rr4.wav` |
| `OH/cowbell_FF_5.wav` | `salamander_cowbell1_hit_main_vl03_rr5.wav` |
| `OH/cowbell_FF_6.wav` | `salamander_cowbell1_hit_main_vl03_rr6.wav` |
| `OH/cowbell_FF_7.wav` | `salamander_cowbell1_hit_main_vl03_rr7.wav` |
| `OH/cowbell_FF_8.wav` | `salamander_cowbell1_hit_main_vl03_rr8.wav` |
| `OH/cowbell_FF_9.wav` | `salamander_cowbell1_hit_main_vl03_rr9.wav` |
| `OH/crash1Choke_OH_F_1.wav` | `salamander_crash1_choke_main_vl01_rr1.wav` |
| `OH/crash1_OH_P_1.wav` | `salamander_crash1_hit_main_vl01_rr1.wav` |
| `OH/crash1_OH_P_2.wav` | `salamander_crash1_hit_main_vl01_rr2.wav` |
| `OH/crash1_OH_P_3.wav` | `salamander_crash1_hit_main_vl01_rr3.wav` |
| `OH/crash1_OH_P_4.wav` | `salamander_crash1_hit_main_vl01_rr4.wav` |
| `OH/crash1_OH_P_5.wav` | `salamander_crash1_hit_main_vl01_rr5.wav` |
| `OH/crash1_OH_FF_1.wav` | `salamander_crash1_hit_main_vl02_rr1.wav` |
| `OH/crash1_OH_FF_2.wav` | `salamander_crash1_hit_main_vl02_rr2.wav` |
| `OH/crash1_OH_FF_3.wav` | `salamander_crash1_hit_main_vl02_rr3.wav` |
| `OH/crash1_OH_FF_4.wav` | `salamander_crash1_hit_main_vl02_rr4.wav` |
| `OH/crash1_OH_FF_5.wav` | `salamander_crash1_hit_main_vl02_rr5.wav` |
| `OH/crash1_OH_FF_6.wav` | `salamander_crash1_hit_main_vl02_rr6.wav` |
| `OH/crash2Choke_OH_F_1.wav` | `salamander_crash2_choke_main_vl01_rr1.wav` |
| `OH/crash2_OH_P_1.wav` | `salamander_crash2_hit_main_vl01_rr1.wav` |
| `OH/crash2_OH_P_2.wav` | `salamander_crash2_hit_main_vl01_rr2.wav` |
| `OH/crash2_OH_P_3.wav` | `salamander_crash2_hit_main_vl01_rr3.wav` |
| `OH/crash2_OH_P_4.wav` | `salamander_crash2_hit_main_vl01_rr4.wav` |
| `OH/crash2_OH_FF_1.wav` | `salamander_crash2_hit_main_vl02_rr1.wav` |
| `OH/crash2_OH_FF_2.wav` | `salamander_crash2_hit_main_vl02_rr2.wav` |
| `OH/crash2_OH_FF_3.wav` | `salamander_crash2_hit_main_vl02_rr3.wav` |
| `OH/crash2_OH_FF_4.wav` | `salamander_crash2_hit_main_vl02_rr4.wav` |
| `OH/crash2_OH_FF_5.wav` | `salamander_crash2_hit_main_vl02_rr5.wav` |
| `OH/crash2_OH_FF_6.wav` | `salamander_crash2_hit_main_vl02_rr6.wav` |
| `OH/crash2_OH_FF_7.wav` | `salamander_crash2_hit_main_vl02_rr7.wav` |
| `OH/crash2_OH_FF_8.wav` | `salamander_crash2_hit_main_vl02_rr8.wav` |
| `OH/crash3_OH_FF_1.wav` | `salamander_crash3_hit_main_vl01_rr1.wav` |
| `OH/crash3_OH_FF_2.wav` | `salamander_crash3_hit_main_vl01_rr2.wav` |
| `OH/crash3_OH_FF_3.wav` | `salamander_crash3_hit_main_vl01_rr3.wav` |
| `OH/crash3_OH_FF_4.wav` | `salamander_crash3_hit_main_vl01_rr4.wav` |
| `OH/crash3_OH_FF_5.wav` | `salamander_crash3_hit_main_vl01_rr5.wav` |
| `OH/crash3_OH_FF_6.wav` | `salamander_crash3_hit_main_vl01_rr6.wav` |
| `OH/crash3_OH_FF_7.wav` | `salamander_crash3_hit_main_vl01_rr7.wav` |
| `OH/crash3_OH_FF_8.wav` | `salamander_crash3_hit_main_vl01_rr8.wav` |
| `OH/hihatClosed_OH_P_1.wav` | `salamander_hihat_closed_main_vl01_rr1.wav` |
| `OH/hihatClosed_OH_P_10.wav` | `salamander_hihat_closed_main_vl01_rr10.wav` |
| `OH/hihatClosed_OH_P_11.wav` | `salamander_hihat_closed_main_vl01_rr11.wav` |
| `OH/hihatClosed_OH_P_12.wav` | `salamander_hihat_closed_main_vl01_rr12.wav` |
| `OH/hihatClosed_OH_P_13.wav` | `salamander_hihat_closed_main_vl01_rr13.wav` |
| `OH/hihatClosed_OH_P_14.wav` | `salamander_hihat_closed_main_vl01_rr14.wav` |
| `OH/hihatClosed_OH_P_15.wav` | `salamander_hihat_closed_main_vl01_rr15.wav` |
| `OH/hihatClosed_OH_P_16.wav` | `salamander_hihat_closed_main_vl01_rr16.wav` |
| `OH/hihatClosed_OH_P_17.wav` | `salamander_hihat_closed_main_vl01_rr17.wav` |
| `OH/hihatClosed_OH_P_18.wav` | `salamander_hihat_closed_main_vl01_rr18.wav` |
| `OH/hihatClosed_OH_P_19.wav` | `salamander_hihat_closed_main_vl01_rr19.wav` |
| `OH/hihatClosed_OH_P_2.wav` | `salamander_hihat_closed_main_vl01_rr2.wav` |
| `OH/hihatClosed_OH_P_20.wav` | `salamander_hihat_closed_main_vl01_rr20.wav` |
| `OH/hihatClosed_OH_P_3.wav` | `salamander_hihat_closed_main_vl01_rr3.wav` |
| `OH/hihatClosed_OH_P_4.wav` | `salamander_hihat_closed_main_vl01_rr4.wav` |
| `OH/hihatClosed_OH_P_5.wav` | `salamander_hihat_closed_main_vl01_rr5.wav` |
| `OH/hihatClosed_OH_P_6.wav` | `salamander_hihat_closed_main_vl01_rr6.wav` |
| `OH/hihatClosed_OH_P_7.wav` | `salamander_hihat_closed_main_vl01_rr7.wav` |
| `OH/hihatClosed_OH_P_8.wav` | `salamander_hihat_closed_main_vl01_rr8.wav` |
| `OH/hihatClosed_OH_P_9.wav` | `salamander_hihat_closed_main_vl01_rr9.wav` |
| `OH/hihatClosed_OH_F_1.wav` | `salamander_hihat_closed_main_vl02_rr1.wav` |
| `OH/hihatClosed_OH_F_10.wav` | `salamander_hihat_closed_main_vl02_rr10.wav` |
| `OH/hihatClosed_OH_F_11.wav` | `salamander_hihat_closed_main_vl02_rr11.wav` |
| `OH/hihatClosed_OH_F_12.wav` | `salamander_hihat_closed_main_vl02_rr12.wav` |
| `OH/hihatClosed_OH_F_13.wav` | `salamander_hihat_closed_main_vl02_rr13.wav` |
| `OH/hihatClosed_OH_F_14.wav` | `salamander_hihat_closed_main_vl02_rr14.wav` |
| `OH/hihatClosed_OH_F_15.wav` | `salamander_hihat_closed_main_vl02_rr15.wav` |
| `OH/hihatClosed_OH_F_16.wav` | `salamander_hihat_closed_main_vl02_rr16.wav` |
| `OH/hihatClosed_OH_F_17.wav` | `salamander_hihat_closed_main_vl02_rr17.wav` |
| `OH/hihatClosed_OH_F_18.wav` | `salamander_hihat_closed_main_vl02_rr18.wav` |
| `OH/hihatClosed_OH_F_19.wav` | `salamander_hihat_closed_main_vl02_rr19.wav` |
| `OH/hihatClosed_OH_F_2.wav` | `salamander_hihat_closed_main_vl02_rr2.wav` |
| `OH/hihatClosed_OH_F_20.wav` | `salamander_hihat_closed_main_vl02_rr20.wav` |
| `OH/hihatClosed_OH_F_3.wav` | `salamander_hihat_closed_main_vl02_rr3.wav` |
| `OH/hihatClosed_OH_F_4.wav` | `salamander_hihat_closed_main_vl02_rr4.wav` |
| `OH/hihatClosed_OH_F_5.wav` | `salamander_hihat_closed_main_vl02_rr5.wav` |
| `OH/hihatClosed_OH_F_6.wav` | `salamander_hihat_closed_main_vl02_rr6.wav` |
| `OH/hihatClosed_OH_F_7.wav` | `salamander_hihat_closed_main_vl02_rr7.wav` |
| `OH/hihatClosed_OH_F_8.wav` | `salamander_hihat_closed_main_vl02_rr8.wav` |
| `OH/hihatClosed_OH_F_9.wav` | `salamander_hihat_closed_main_vl02_rr9.wav` |
| `OH/hihatSemiOpen7_OH_P_1.wav` | `salamander_hihat_edge_main_vl01_rr1.wav` |
| `OH/hihatSemiOpen7_OH_P_2.wav` | `salamander_hihat_edge_main_vl01_rr2.wav` |
| `OH/hihatSemiOpen7_OH_P_3.wav` | `salamander_hihat_edge_main_vl01_rr3.wav` |
| `OH/hihatSemiOpen7_OH_P_4.wav` | `salamander_hihat_edge_main_vl01_rr4.wav` |
| `OH/hihatSemiOpen7_OH_P_5.wav` | `salamander_hihat_edge_main_vl01_rr5.wav` |
| `OH/hihatSemiOpen7_OH_F_1.wav` | `salamander_hihat_edge_main_vl02_rr1.wav` |
| `OH/hihatSemiOpen7_OH_F_2.wav` | `salamander_hihat_edge_main_vl02_rr2.wav` |
| `OH/hihatSemiOpen7_OH_F_3.wav` | `salamander_hihat_edge_main_vl02_rr3.wav` |
| `OH/hihatSemiOpen7_OH_F_4.wav` | `salamander_hihat_edge_main_vl02_rr4.wav` |
| `OH/hihatSemiOpen7_OH_F_5.wav` | `salamander_hihat_edge_main_vl02_rr5.wav` |
| `OH/hihatFoot_OH_MP_1.wav` | `salamander_hihat_foot_main_vl01_rr1.wav` |
| `OH/hihatFoot_OH_MP_10.wav` | `salamander_hihat_foot_main_vl01_rr10.wav` |
| `OH/hihatFoot_OH_MP_11.wav` | `salamander_hihat_foot_main_vl01_rr11.wav` |
| `OH/hihatFoot_OH_MP_12.wav` | `salamander_hihat_foot_main_vl01_rr12.wav` |
| `OH/hihatFoot_OH_MP_2.wav` | `salamander_hihat_foot_main_vl01_rr2.wav` |
| `OH/hihatFoot_OH_MP_3.wav` | `salamander_hihat_foot_main_vl01_rr3.wav` |
| `OH/hihatFoot_OH_MP_4.wav` | `salamander_hihat_foot_main_vl01_rr4.wav` |
| `OH/hihatFoot_OH_MP_5.wav` | `salamander_hihat_foot_main_vl01_rr5.wav` |
| `OH/hihatFoot_OH_MP_6.wav` | `salamander_hihat_foot_main_vl01_rr6.wav` |
| `OH/hihatFoot_OH_MP_7.wav` | `salamander_hihat_foot_main_vl01_rr7.wav` |
| `OH/hihatFoot_OH_MP_8.wav` | `salamander_hihat_foot_main_vl01_rr8.wav` |
| `OH/hihatFoot_OH_MP_9.wav` | `salamander_hihat_foot_main_vl01_rr9.wav` |
| `OH/hihatFootStomp_OH_MP_1.wav` | `salamander_hihat_footsplash_main_vl01_rr1.wav` |
| `OH/hihatFootStomp_OH_MP_2.wav` | `salamander_hihat_footsplash_main_vl01_rr2.wav` |
| `OH/hihatFootStomp_OH_MP_3.wav` | `salamander_hihat_footsplash_main_vl01_rr3.wav` |
| `OH/hihatFootStomp_OH_MP_4.wav` | `salamander_hihat_footsplash_main_vl01_rr4.wav` |
| `OH/hihatSemiOpen3_OH_P_1.wav` | `salamander_hihat_half_main_vl01_rr1.wav` |
| `OH/hihatSemiOpen3_OH_P_2.wav` | `salamander_hihat_half_main_vl01_rr2.wav` |
| `OH/hihatSemiOpen3_OH_P_3.wav` | `salamander_hihat_half_main_vl01_rr3.wav` |
| `OH/hihatSemiOpen3_OH_P_4.wav` | `salamander_hihat_half_main_vl01_rr4.wav` |
| `OH/hihatSemiOpen3_OH_P_5.wav` | `salamander_hihat_half_main_vl01_rr5.wav` |
| `OH/hihatSemiOpen3_OH_F_1.wav` | `salamander_hihat_half_main_vl02_rr1.wav` |
| `OH/hihatSemiOpen3_OH_F_2.wav` | `salamander_hihat_half_main_vl02_rr2.wav` |
| `OH/hihatSemiOpen3_OH_F_3.wav` | `salamander_hihat_half_main_vl02_rr3.wav` |
| `OH/hihatSemiOpen3_OH_F_4.wav` | `salamander_hihat_half_main_vl02_rr4.wav` |
| `OH/hihatSemiOpen3_OH_F_5.wav` | `salamander_hihat_half_main_vl02_rr5.wav` |
| `OH/hihatSemiOpen4_OH_P_1.wav` | `salamander_hihat_loose_main_vl01_rr1.wav` |
| `OH/hihatSemiOpen4_OH_P_2.wav` | `salamander_hihat_loose_main_vl01_rr2.wav` |
| `OH/hihatSemiOpen4_OH_P_3.wav` | `salamander_hihat_loose_main_vl01_rr3.wav` |
| `OH/hihatSemiOpen4_OH_P_4.wav` | `salamander_hihat_loose_main_vl01_rr4.wav` |
| `OH/hihatSemiOpen4_OH_P_5.wav` | `salamander_hihat_loose_main_vl01_rr5.wav` |
| `OH/hihatSemiOpen4_OH_F_1.wav` | `salamander_hihat_loose_main_vl02_rr1.wav` |
| `OH/hihatSemiOpen4_OH_F_2.wav` | `salamander_hihat_loose_main_vl02_rr2.wav` |
| `OH/hihatSemiOpen4_OH_F_3.wav` | `salamander_hihat_loose_main_vl02_rr3.wav` |
| `OH/hihatSemiOpen4_OH_F_4.wav` | `salamander_hihat_loose_main_vl02_rr4.wav` |
| `OH/hihatSemiOpen4_OH_F_5.wav` | `salamander_hihat_loose_main_vl02_rr5.wav` |
| `OH/hihatOpen_OH_P_1.wav` | `salamander_hihat_open_main_vl01_rr1.wav` |
| `OH/hihatOpen_OH_P_2.wav` | `salamander_hihat_open_main_vl01_rr2.wav` |
| `OH/hihatOpen_OH_P_3.wav` | `salamander_hihat_open_main_vl01_rr3.wav` |
| `OH/hihatOpen_OH_P_4.wav` | `salamander_hihat_open_main_vl01_rr4.wav` |
| `OH/hihatOpen_OH_P_5.wav` | `salamander_hihat_open_main_vl01_rr5.wav` |
| `OH/hihatOpen_OH_P_6.wav` | `salamander_hihat_open_main_vl01_rr6.wav` |
| `OH/hihatOpen_OH_P_7.wav` | `salamander_hihat_open_main_vl01_rr7.wav` |
| `OH/hihatOpen_OH_F_1.wav` | `salamander_hihat_open_main_vl02_rr1.wav` |
| `OH/hihatOpen_OH_F_2.wav` | `salamander_hihat_open_main_vl02_rr2.wav` |
| `OH/hihatOpen_OH_F_3.wav` | `salamander_hihat_open_main_vl02_rr3.wav` |
| `OH/hihatOpen_OH_F_4.wav` | `salamander_hihat_open_main_vl02_rr4.wav` |
| `OH/hihatOpen_OH_F_5.wav` | `salamander_hihat_open_main_vl02_rr5.wav` |
| `OH/hihatOpen_OH_FF_1.wav` | `salamander_hihat_open_main_vl03_rr1.wav` |
| `OH/hihatOpen_OH_FF_2.wav` | `salamander_hihat_open_main_vl03_rr2.wav` |
| `OH/hihatOpen_OH_FF_3.wav` | `salamander_hihat_open_main_vl03_rr3.wav` |
| `OH/hihatOpen_OH_FF_4.wav` | `salamander_hihat_open_main_vl03_rr4.wav` |
| `OH/hihatOpen_OH_FF_5.wav` | `salamander_hihat_open_main_vl03_rr5.wav` |
| `OH/hihatOpen_OH_FF_6.wav` | `salamander_hihat_open_main_vl03_rr6.wav` |
| `OH/hihatSemiOpen2_OH_P_1.wav` | `salamander_hihat_quarter_main_vl01_rr1.wav` |
| `OH/hihatSemiOpen2_OH_P_2.wav` | `salamander_hihat_quarter_main_vl01_rr2.wav` |
| `OH/hihatSemiOpen2_OH_P_3.wav` | `salamander_hihat_quarter_main_vl01_rr3.wav` |
| `OH/hihatSemiOpen2_OH_P_4.wav` | `salamander_hihat_quarter_main_vl01_rr4.wav` |
| `OH/hihatSemiOpen2_OH_P_5.wav` | `salamander_hihat_quarter_main_vl01_rr5.wav` |
| `OH/hihatSemiOpen2_OH_F_1.wav` | `salamander_hihat_quarter_main_vl02_rr1.wav` |
| `OH/hihatSemiOpen2_OH_F_2.wav` | `salamander_hihat_quarter_main_vl02_rr2.wav` |
| `OH/hihatSemiOpen2_OH_F_3.wav` | `salamander_hihat_quarter_main_vl02_rr3.wav` |
| `OH/hihatSemiOpen2_OH_F_4.wav` | `salamander_hihat_quarter_main_vl02_rr4.wav` |
| `OH/hihatSemiOpen2_OH_F_5.wav` | `salamander_hihat_quarter_main_vl02_rr5.wav` |
| `OH/hihatSemiOpen6_OH_P_1.wav` | `salamander_hihat_shank_main_vl01_rr1.wav` |
| `OH/hihatSemiOpen6_OH_P_2.wav` | `salamander_hihat_shank_main_vl01_rr2.wav` |
| `OH/hihatSemiOpen6_OH_P_3.wav` | `salamander_hihat_shank_main_vl01_rr3.wav` |
| `OH/hihatSemiOpen6_OH_P_4.wav` | `salamander_hihat_shank_main_vl01_rr4.wav` |
| `OH/hihatSemiOpen6_OH_P_5.wav` | `salamander_hihat_shank_main_vl01_rr5.wav` |
| `OH/hihatSemiOpen6_OH_F_1.wav` | `salamander_hihat_shank_main_vl02_rr1.wav` |
| `OH/hihatSemiOpen6_OH_F_2.wav` | `salamander_hihat_shank_main_vl02_rr2.wav` |
| `OH/hihatSemiOpen6_OH_F_3.wav` | `salamander_hihat_shank_main_vl02_rr3.wav` |
| `OH/hihatSemiOpen6_OH_F_4.wav` | `salamander_hihat_shank_main_vl02_rr4.wav` |
| `OH/hihatSemiOpen6_OH_F_5.wav` | `salamander_hihat_shank_main_vl02_rr5.wav` |
| `OH/hihatSemiOpen1_OH_P_1.wav` | `salamander_hihat_tight_main_vl01_rr1.wav` |
| `OH/hihatSemiOpen1_OH_P_2.wav` | `salamander_hihat_tight_main_vl01_rr2.wav` |
| `OH/hihatSemiOpen1_OH_P_3.wav` | `salamander_hihat_tight_main_vl01_rr3.wav` |
| `OH/hihatSemiOpen1_OH_P_4.wav` | `salamander_hihat_tight_main_vl01_rr4.wav` |
| `OH/hihatSemiOpen1_OH_P_5.wav` | `salamander_hihat_tight_main_vl01_rr5.wav` |
| `OH/hihatSemiOpen1_OH_P_.wav` | `salamander_hihat_tight_main_vl01_rr6.wav` |
| `OH/hihatSemiOpen1_OH_F_1.wav` | `salamander_hihat_tight_main_vl02_rr1.wav` |
| `OH/hihatSemiOpen1_OH_F_2.wav` | `salamander_hihat_tight_main_vl02_rr2.wav` |
| `OH/hihatSemiOpen1_OH_F_3.wav` | `salamander_hihat_tight_main_vl02_rr3.wav` |
| `OH/hihatSemiOpen1_OH_F_4.wav` | `salamander_hihat_tight_main_vl02_rr4.wav` |
| `OH/hihatSemiOpen1_OH_F_5.wav` | `salamander_hihat_tight_main_vl02_rr5.wav` |
| `OH/hihatSemiOpen5_OH_P_1.wav` | `salamander_hihat_tip_main_vl01_rr1.wav` |
| `OH/hihatSemiOpen5_OH_P_2.wav` | `salamander_hihat_tip_main_vl01_rr2.wav` |
| `OH/hihatSemiOpen5_OH_P_3.wav` | `salamander_hihat_tip_main_vl01_rr3.wav` |
| `OH/hihatSemiOpen5_OH_P_4.wav` | `salamander_hihat_tip_main_vl01_rr4.wav` |
| `OH/hihatSemiOpen5_OH_P_5.wav` | `salamander_hihat_tip_main_vl01_rr5.wav` |
| `OH/hihatSemiOpen5_OH_F_1.wav` | `salamander_hihat_tip_main_vl02_rr1.wav` |
| `OH/hihatSemiOpen5_OH_F_2.wav` | `salamander_hihat_tip_main_vl02_rr2.wav` |
| `OH/hihatSemiOpen5_OH_F_3.wav` | `salamander_hihat_tip_main_vl02_rr3.wav` |
| `OH/hihatSemiOpen5_OH_F_4.wav` | `salamander_hihat_tip_main_vl02_rr4.wav` |
| `OH/hihatSemiOpen5_OH_F_5.wav` | `salamander_hihat_tip_main_vl02_rr5.wav` |
| `OH/kick_OH_P_1.wav` | `salamander_kick1_hit_main_vl01_rr1.wav` |
| `OH/kick_OH_P_2.wav` | `salamander_kick1_hit_main_vl01_rr2.wav` |
| `OH/kick_OH_P_3.wav` | `salamander_kick1_hit_main_vl01_rr3.wav` |
| `OH/kick_OH_P_4.wav` | `salamander_kick1_hit_main_vl01_rr4.wav` |
| `OH/kick_OH_P_5.wav` | `salamander_kick1_hit_main_vl01_rr5.wav` |
| `OH/kick_OH_P_6.wav` | `salamander_kick1_hit_main_vl01_rr6.wav` |
| `OH/kick_OH_P_7.wav` | `salamander_kick1_hit_main_vl01_rr7.wav` |
| `OH/kick_OH_P_8.wav` | `salamander_kick1_hit_main_vl01_rr8.wav` |
| `OH/kick_OH_P_9.wav` | `salamander_kick1_hit_main_vl01_rr9.wav` |
| `OH/kick_OH_F_1.wav` | `salamander_kick1_hit_main_vl02_rr1.wav` |
| `OH/kick_OH_F_10.wav` | `salamander_kick1_hit_main_vl02_rr10.wav` |
| `OH/kick_OH_F_11.wav` | `salamander_kick1_hit_main_vl02_rr11.wav` |
| `OH/kick_OH_F_2.wav` | `salamander_kick1_hit_main_vl02_rr2.wav` |
| `OH/kick_OH_F_3.wav` | `salamander_kick1_hit_main_vl02_rr3.wav` |
| `OH/kick_OH_F_4.wav` | `salamander_kick1_hit_main_vl02_rr4.wav` |
| `OH/kick_OH_F_5.wav` | `salamander_kick1_hit_main_vl02_rr5.wav` |
| `OH/kick_OH_F_6.wav` | `salamander_kick1_hit_main_vl02_rr6.wav` |
| `OH/kick_OH_F_7.wav` | `salamander_kick1_hit_main_vl02_rr7.wav` |
| `OH/kick_OH_F_8.wav` | `salamander_kick1_hit_main_vl02_rr8.wav` |
| `OH/kick_OH_F_9.wav` | `salamander_kick1_hit_main_vl02_rr9.wav` |
| `OH/kick_OH_FF_1.wav` | `salamander_kick1_hit_main_vl03_rr1.wav` |
| `OH/kick_OH_FF_10.wav` | `salamander_kick1_hit_main_vl03_rr10.wav` |
| `OH/kick_OH_FF_11.wav` | `salamander_kick1_hit_main_vl03_rr11.wav` |
| `OH/kick_OH_FF_12.wav` | `salamander_kick1_hit_main_vl03_rr12.wav` |
| `OH/kick_OH_FF_2.wav` | `salamander_kick1_hit_main_vl03_rr2.wav` |
| `OH/kick_OH_FF_3.wav` | `salamander_kick1_hit_main_vl03_rr3.wav` |
| `OH/kick_OH_FF_4.wav` | `salamander_kick1_hit_main_vl03_rr4.wav` |
| `OH/kick_OH_FF_5.wav` | `salamander_kick1_hit_main_vl03_rr5.wav` |
| `OH/kick_OH_FF_6.wav` | `salamander_kick1_hit_main_vl03_rr6.wav` |
| `OH/kick_OH_FF_7.wav` | `salamander_kick1_hit_main_vl03_rr7.wav` |
| `OH/kick_OH_FF_8.wav` | `salamander_kick1_hit_main_vl03_rr8.wav` |
| `OH/kick_OH_FF_9.wav` | `salamander_kick1_hit_main_vl03_rr9.wav` |
| `OH/kick2_OH_P_1.wav` | `salamander_kick2_hit_main_vl01_rr1.wav` |
| `OH/kick2_OH_P_2.wav` | `salamander_kick2_hit_main_vl01_rr2.wav` |
| `OH/kick2_OH_P_3.wav` | `salamander_kick2_hit_main_vl01_rr3.wav` |
| `OH/kick2_OH_P_4.wav` | `salamander_kick2_hit_main_vl01_rr4.wav` |
| `OH/kick2_OH_P_5.wav` | `salamander_kick2_hit_main_vl01_rr5.wav` |
| `OH/kick2_OH_P_6.wav` | `salamander_kick2_hit_main_vl01_rr6.wav` |
| `OH/kick2_OH_P_7.wav` | `salamander_kick2_hit_main_vl01_rr7.wav` |
| `OH/kick2_OH_P_8.wav` | `salamander_kick2_hit_main_vl01_rr8.wav` |
| `OH/kick2_OH_P_9.wav` | `salamander_kick2_hit_main_vl01_rr9.wav` |
| `OH/kick2_OH_F_1.wav` | `salamander_kick2_hit_main_vl02_rr1.wav` |
| `OH/kick2_OH_F_10.wav` | `salamander_kick2_hit_main_vl02_rr10.wav` |
| `OH/kick2_OH_F_11.wav` | `salamander_kick2_hit_main_vl02_rr11.wav` |
| `OH/kick2_OH_F_2.wav` | `salamander_kick2_hit_main_vl02_rr2.wav` |
| `OH/kick2_OH_F_3.wav` | `salamander_kick2_hit_main_vl02_rr3.wav` |
| `OH/kick2_OH_F_4.wav` | `salamander_kick2_hit_main_vl02_rr4.wav` |
| `OH/kick2_OH_F_5.wav` | `salamander_kick2_hit_main_vl02_rr5.wav` |
| `OH/kick2_OH_F_6.wav` | `salamander_kick2_hit_main_vl02_rr6.wav` |
| `OH/kick2_OH_F_7.wav` | `salamander_kick2_hit_main_vl02_rr7.wav` |
| `OH/kick2_OH_F_8.wav` | `salamander_kick2_hit_main_vl02_rr8.wav` |
| `OH/kick2_OH_F_9.wav` | `salamander_kick2_hit_main_vl02_rr9.wav` |
| `OH/kick2_OH_FF_1.wav` | `salamander_kick2_hit_main_vl03_rr1.wav` |
| `OH/kick2_OH_FF_10.wav` | `salamander_kick2_hit_main_vl03_rr10.wav` |
| `OH/kick2_OH_FF_11.wav` | `salamander_kick2_hit_main_vl03_rr11.wav` |
| `OH/kick2_OH_FF_12.wav` | `salamander_kick2_hit_main_vl03_rr12.wav` |
| `OH/kick2_OH_FF_2.wav` | `salamander_kick2_hit_main_vl03_rr2.wav` |
| `OH/kick2_OH_FF_3.wav` | `salamander_kick2_hit_main_vl03_rr3.wav` |
| `OH/kick2_OH_FF_4.wav` | `salamander_kick2_hit_main_vl03_rr4.wav` |
| `OH/kick2_OH_FF_5.wav` | `salamander_kick2_hit_main_vl03_rr5.wav` |
| `OH/kick2_OH_FF_6.wav` | `salamander_kick2_hit_main_vl03_rr6.wav` |
| `OH/kick2_OH_FF_7.wav` | `salamander_kick2_hit_main_vl03_rr7.wav` |
| `OH/kick2_OH_FF_8.wav` | `salamander_kick2_hit_main_vl03_rr8.wav` |
| `OH/kick2_OH_FF_9.wav` | `salamander_kick2_hit_main_vl03_rr9.wav` |
| `OH/bellchime_F_1.wav` | `salamander_other_bell_main_vl01_rr1.wav` |
| `OH/bellchime_F_2.wav` | `salamander_other_bell_main_vl01_rr2.wav` |
| `OH/bellchime_F_3.wav` | `salamander_other_bell_main_vl01_rr3.wav` |
| `OH/ride1Bell_OH_F_1.wav` | `salamander_ride1_bell_main_vl01_rr1.wav` |
| `OH/ride1Bell_OH_F_2.wav` | `salamander_ride1_bell_main_vl01_rr2.wav` |
| `OH/ride1Bell_OH_F_3.wav` | `salamander_ride1_bell_main_vl01_rr3.wav` |
| `OH/ride1Bell_OH_F_4.wav` | `salamander_ride1_bell_main_vl01_rr4.wav` |
| `OH/ride1Bell_OH_F_5.wav` | `salamander_ride1_bell_main_vl01_rr5.wav` |
| `OH/ride1Bell_OH_F_6.wav` | `salamander_ride1_bell_main_vl01_rr6.wav` |
| `OH/ride1_OH_MP_1.wav` | `salamander_ride1_hit_main_vl01_rr1.wav` |
| `OH/ride1_OH_MP_2.wav` | `salamander_ride1_hit_main_vl01_rr2.wav` |
| `OH/ride1_OH_MP_3.wav` | `salamander_ride1_hit_main_vl01_rr3.wav` |
| `OH/ride1_OH_MP_4.wav` | `salamander_ride1_hit_main_vl01_rr4.wav` |
| `OH/ride1_OH_MP_5.wav` | `salamander_ride1_hit_main_vl01_rr5.wav` |
| `OH/ride1_OH_MP_6.wav` | `salamander_ride1_hit_main_vl01_rr6.wav` |
| `OH/ride1_OH_MP_7.wav` | `salamander_ride1_hit_main_vl01_rr7.wav` |
| `OH/ride1_OH_MP_8.wav` | `salamander_ride1_hit_main_vl01_rr8.wav` |
| `OH/ride1_OH_FF_1.wav` | `salamander_ride1_hit_main_vl02_rr1.wav` |
| `OH/ride1_OH_FF_2.wav` | `salamander_ride1_hit_main_vl02_rr2.wav` |
| `OH/ride1_OH_FF_3.wav` | `salamander_ride1_hit_main_vl02_rr3.wav` |
| `OH/ride1_OH_FF_4.wav` | `salamander_ride1_hit_main_vl02_rr4.wav` |
| `OH/ride2Bell_OH_F_1.wav` | `salamander_ride2_bell_main_vl01_rr1.wav` |
| `OH/ride2Bell_OH_F_2.wav` | `salamander_ride2_bell_main_vl01_rr2.wav` |
| `OH/ride2Bell_OH_F_3.wav` | `salamander_ride2_bell_main_vl01_rr3.wav` |
| `OH/ride2Bell_OH_F_4.wav` | `salamander_ride2_bell_main_vl01_rr4.wav` |
| `OH/ride2Bell_OH_F_5.wav` | `salamander_ride2_bell_main_vl01_rr5.wav` |
| `OH/ride2Bell_OH_F_6.wav` | `salamander_ride2_bell_main_vl01_rr6.wav` |
| `OH/ride2CrashChoke_OH_F_1.wav` | `salamander_ride2_choke_main_vl01_rr1.wav` |
| `OH/ride2Crash_OH_MP_1.wav` | `salamander_ride2_edge_main_vl01_rr1.wav` |
| `OH/ride2Crash_OH_MP_2.wav` | `salamander_ride2_edge_main_vl01_rr2.wav` |
| `OH/ride2Crash_OH_MP_3.wav` | `salamander_ride2_edge_main_vl01_rr3.wav` |
| `OH/ride2Crash_OH_FF_1.wav` | `salamander_ride2_edge_main_vl02_rr1.wav` |
| `OH/ride2Crash_OH_FF_2.wav` | `salamander_ride2_edge_main_vl02_rr2.wav` |
| `OH/ride2Crash_OH_FF_3.wav` | `salamander_ride2_edge_main_vl02_rr3.wav` |
| `OH/ride2Crash_OH_FF_4.wav` | `salamander_ride2_edge_main_vl02_rr4.wav` |
| `OH/ride2Crash_OH_FF_5.wav` | `salamander_ride2_edge_main_vl02_rr5.wav` |
| `OH/ride2Crash_OH_FF_6.wav` | `salamander_ride2_edge_main_vl02_rr6.wav` |
| `OH/ride2_OH_PP_1.wav` | `salamander_ride2_hit_main_vl01_rr1.wav` |
| `OH/ride2_OH_PP_2.wav` | `salamander_ride2_hit_main_vl01_rr2.wav` |
| `OH/ride2_OH_PP_3.wav` | `salamander_ride2_hit_main_vl01_rr3.wav` |
| `OH/ride2_OH_PP_4.wav` | `salamander_ride2_hit_main_vl01_rr4.wav` |
| `OH/ride2_OH_MP_1.wav` | `salamander_ride2_hit_main_vl02_rr1.wav` |
| `OH/ride2_OH_MP_2.wav` | `salamander_ride2_hit_main_vl02_rr2.wav` |
| `OH/ride2_OH_MP_3.wav` | `salamander_ride2_hit_main_vl02_rr3.wav` |
| `OH/ride2_OH_MP_4.wav` | `salamander_ride2_hit_main_vl02_rr4.wav` |
| `OH/ride2_OH_MP_5.wav` | `salamander_ride2_hit_main_vl02_rr5.wav` |
| `OH/ride2_OH_MP_6.wav` | `salamander_ride2_hit_main_vl02_rr6.wav` |
| `OH/ride2_OH_MP_7.wav` | `salamander_ride2_hit_main_vl02_rr7.wav` |
| `OH/ride2_OH_MP_8.wav` | `salamander_ride2_hit_main_vl02_rr8.wav` |
| `OH/ride2_OH_FF_1.wav` | `salamander_ride2_hit_main_vl03_rr1.wav` |
| `OH/ride2_OH_FF_2.wav` | `salamander_ride2_hit_main_vl03_rr2.wav` |
| `OH/ride2_OH_FF_3.wav` | `salamander_ride2_hit_main_vl03_rr3.wav` |
| `OH/ride2_OH_FF_4.wav` | `salamander_ride2_hit_main_vl03_rr4.wav` |
| `OH/ride2_OH_FF_5.wav` | `salamander_ride2_hit_main_vl03_rr5.wav` |
| `OH/snare_OH_Ghost_1.wav` | `salamander_snare1_hit_main_vl01_rr1.wav` |
| `OH/snare_OH_Ghost_10.wav` | `salamander_snare1_hit_main_vl01_rr10.wav` |
| `OH/snare_OH_Ghost_2.wav` | `salamander_snare1_hit_main_vl01_rr2.wav` |
| `OH/snare_OH_Ghost_3.wav` | `salamander_snare1_hit_main_vl01_rr3.wav` |
| `OH/snare_OH_Ghost_4.wav` | `salamander_snare1_hit_main_vl01_rr4.wav` |
| `OH/snare_OH_Ghost_5.wav` | `salamander_snare1_hit_main_vl01_rr5.wav` |
| `OH/snare_OH_Ghost_6.wav` | `salamander_snare1_hit_main_vl01_rr6.wav` |
| `OH/snare_OH_Ghost_7.wav` | `salamander_snare1_hit_main_vl01_rr7.wav` |
| `OH/snare_OH_Ghost_8.wav` | `salamander_snare1_hit_main_vl01_rr8.wav` |
| `OH/snare_OH_Ghost_9.wav` | `salamander_snare1_hit_main_vl01_rr9.wav` |
| `OH/snare_OH_MP_1.wav` | `salamander_snare1_hit_main_vl02_rr1.wav` |
| `OH/snare_OH_MP_10.wav` | `salamander_snare1_hit_main_vl02_rr10.wav` |
| `OH/snare_OH_MP_11.wav` | `salamander_snare1_hit_main_vl02_rr11.wav` |
| `OH/snare_OH_MP_12.wav` | `salamander_snare1_hit_main_vl02_rr12.wav` |
| `OH/snare_OH_MP_13.wav` | `salamander_snare1_hit_main_vl02_rr13.wav` |
| `OH/snare_OH_MP_14.wav` | `salamander_snare1_hit_main_vl02_rr14.wav` |
| `OH/snare_OH_MP_2.wav` | `salamander_snare1_hit_main_vl02_rr2.wav` |
| `OH/snare_OH_MP_3.wav` | `salamander_snare1_hit_main_vl02_rr3.wav` |
| `OH/snare_OH_MP_4.wav` | `salamander_snare1_hit_main_vl02_rr4.wav` |
| `OH/snare_OH_MP_5.wav` | `salamander_snare1_hit_main_vl02_rr5.wav` |
| `OH/snare_OH_MP_6.wav` | `salamander_snare1_hit_main_vl02_rr6.wav` |
| `OH/snare_OH_MP_7.wav` | `salamander_snare1_hit_main_vl02_rr7.wav` |
| `OH/snare_OH_MP_8.wav` | `salamander_snare1_hit_main_vl02_rr8.wav` |
| `OH/snare_OH_MP_9.wav` | `salamander_snare1_hit_main_vl02_rr9.wav` |
| `OH/snare_OH_F_1.wav` | `salamander_snare1_hit_main_vl03_rr1.wav` |
| `OH/snare_OH_F_10.wav` | `salamander_snare1_hit_main_vl03_rr10.wav` |
| `OH/snare_OH_F_11.wav` | `salamander_snare1_hit_main_vl03_rr11.wav` |
| `OH/snare_OH_F_12.wav` | `salamander_snare1_hit_main_vl03_rr12.wav` |
| `OH/snare_OH_F_2.wav` | `salamander_snare1_hit_main_vl03_rr2.wav` |
| `OH/snare_OH_F_3.wav` | `salamander_snare1_hit_main_vl03_rr3.wav` |
| `OH/snare_OH_F_4.wav` | `salamander_snare1_hit_main_vl03_rr4.wav` |
| `OH/snare_OH_F_5.wav` | `salamander_snare1_hit_main_vl03_rr5.wav` |
| `OH/snare_OH_F_6.wav` | `salamander_snare1_hit_main_vl03_rr6.wav` |
| `OH/snare_OH_F_7.wav` | `salamander_snare1_hit_main_vl03_rr7.wav` |
| `OH/snare_OH_F_8.wav` | `salamander_snare1_hit_main_vl03_rr8.wav` |
| `OH/snare_OH_F_9.wav` | `salamander_snare1_hit_main_vl03_rr9.wav` |
| `OH/snare_OH_FF_1.wav` | `salamander_snare1_hit_main_vl04_rr1.wav` |
| `OH/snare_OH_FF_2.wav` | `salamander_snare1_hit_main_vl04_rr2.wav` |
| `OH/snare_OH_FF_3.wav` | `salamander_snare1_hit_main_vl04_rr3.wav` |
| `OH/snare_OH_FF_4.wav` | `salamander_snare1_hit_main_vl04_rr4.wav` |
| `OH/snare_OH_FF_5.wav` | `salamander_snare1_hit_main_vl04_rr5.wav` |
| `OH/snare_OH_FF_6.wav` | `salamander_snare1_hit_main_vl04_rr6.wav` |
| `OH/snare_OH_FF_7.wav` | `salamander_snare1_hit_main_vl04_rr7.wav` |
| `OH/snare_OH_FF_8.wav` | `salamander_snare1_hit_main_vl04_rr8.wav` |
| `OH/snare_OH_FF_9.wav` | `salamander_snare1_hit_main_vl04_rr9.wav` |
| `OH/snareOFF_OH_P_1.wav` | `salamander_snare1_mute_main_vl01_rr1.wav` |
| `OH/snareOFF_OH_P_2.wav` | `salamander_snare1_mute_main_vl01_rr2.wav` |
| `OH/snareOFF_OH_P_3.wav` | `salamander_snare1_mute_main_vl01_rr3.wav` |
| `OH/snareOFF_OH_P_4.wav` | `salamander_snare1_mute_main_vl01_rr4.wav` |
| `OH/snareOFF_OH_P_5.wav` | `salamander_snare1_mute_main_vl01_rr5.wav` |
| `OH/snareOFF_OH_F_1.wav` | `salamander_snare1_mute_main_vl02_rr1.wav` |
| `OH/snareOFF_OH_F_10.wav` | `salamander_snare1_mute_main_vl02_rr10.wav` |
| `OH/snareOFF_OH_F_2.wav` | `salamander_snare1_mute_main_vl02_rr2.wav` |
| `OH/snareOFF_OH_F_3.wav` | `salamander_snare1_mute_main_vl02_rr3.wav` |
| `OH/snareOFF_OH_F_4.wav` | `salamander_snare1_mute_main_vl02_rr4.wav` |
| `OH/snareOFF_OH_F_5.wav` | `salamander_snare1_mute_main_vl02_rr5.wav` |
| `OH/snareOFF_OH_F_6.wav` | `salamander_snare1_mute_main_vl02_rr6.wav` |
| `OH/snareOFF_OH_F_7.wav` | `salamander_snare1_mute_main_vl02_rr7.wav` |
| `OH/snareOFF_OH_F_8.wav` | `salamander_snare1_mute_main_vl02_rr8.wav` |
| `OH/snareOFF_OH_F_9.wav` | `salamander_snare1_mute_main_vl02_rr9.wav` |
| `OH/snareStick_OH_F_1.wav` | `salamander_snare1_sidestick_main_vl01_rr1.wav` |
| `OH/snareStick_OH_F_10.wav` | `salamander_snare1_sidestick_main_vl01_rr10.wav` |
| `OH/snareStick_OH_F_2.wav` | `salamander_snare1_sidestick_main_vl01_rr2.wav` |
| `OH/snareStick_OH_F_3.wav` | `salamander_snare1_sidestick_main_vl01_rr3.wav` |
| `OH/snareStick_OH_F_4.wav` | `salamander_snare1_sidestick_main_vl01_rr4.wav` |
| `OH/snareStick_OH_F_5.wav` | `salamander_snare1_sidestick_main_vl01_rr5.wav` |
| `OH/snareStick_OH_F_6.wav` | `salamander_snare1_sidestick_main_vl01_rr6.wav` |
| `OH/snareStick_OH_F_7.wav` | `salamander_snare1_sidestick_main_vl01_rr7.wav` |
| `OH/snareStick_OH_F_8.wav` | `salamander_snare1_sidestick_main_vl01_rr8.wav` |
| `OH/snareStick_OH_F_9.wav` | `salamander_snare1_sidestick_main_vl01_rr9.wav` |
| `OH/snare2_OH_Ghost_1.wav` | `salamander_snare2_hit_main_vl01_rr1.wav` |
| `OH/snare2_OH_Ghost_10.wav` | `salamander_snare2_hit_main_vl01_rr10.wav` |
| `OH/snare2_OH_Ghost_2.wav` | `salamander_snare2_hit_main_vl01_rr2.wav` |
| `OH/snare2_OH_Ghost_3.wav` | `salamander_snare2_hit_main_vl01_rr3.wav` |
| `OH/snare2_OH_Ghost_4.wav` | `salamander_snare2_hit_main_vl01_rr4.wav` |
| `OH/snare2_OH_Ghost_5.wav` | `salamander_snare2_hit_main_vl01_rr5.wav` |
| `OH/snare2_OH_Ghost_6.wav` | `salamander_snare2_hit_main_vl01_rr6.wav` |
| `OH/snare2_OH_Ghost_7.wav` | `salamander_snare2_hit_main_vl01_rr7.wav` |
| `OH/snare2_OH_Ghost_8.wav` | `salamander_snare2_hit_main_vl01_rr8.wav` |
| `OH/snare2_OH_Ghost_9.wav` | `salamander_snare2_hit_main_vl01_rr9.wav` |
| `OH/snare2_OH_MP_1.wav` | `salamander_snare2_hit_main_vl02_rr1.wav` |
| `OH/snare2_OH_MP_10.wav` | `salamander_snare2_hit_main_vl02_rr10.wav` |
| `OH/snare2_OH_MP_11.wav` | `salamander_snare2_hit_main_vl02_rr11.wav` |
| `OH/snare2_OH_MP_12.wav` | `salamander_snare2_hit_main_vl02_rr12.wav` |
| `OH/snare2_OH_MP_13.wav` | `salamander_snare2_hit_main_vl02_rr13.wav` |
| `OH/snare2_OH_MP_14.wav` | `salamander_snare2_hit_main_vl02_rr14.wav` |
| `OH/snare2_OH_MP_2.wav` | `salamander_snare2_hit_main_vl02_rr2.wav` |
| `OH/snare2_OH_MP_3.wav` | `salamander_snare2_hit_main_vl02_rr3.wav` |
| `OH/snare2_OH_MP_4.wav` | `salamander_snare2_hit_main_vl02_rr4.wav` |
| `OH/snare2_OH_MP_5.wav` | `salamander_snare2_hit_main_vl02_rr5.wav` |
| `OH/snare2_OH_MP_6.wav` | `salamander_snare2_hit_main_vl02_rr6.wav` |
| `OH/snare2_OH_MP_7.wav` | `salamander_snare2_hit_main_vl02_rr7.wav` |
| `OH/snare2_OH_MP_8.wav` | `salamander_snare2_hit_main_vl02_rr8.wav` |
| `OH/snare2_OH_MP_9.wav` | `salamander_snare2_hit_main_vl02_rr9.wav` |
| `OH/snare2_OH_F_1.wav` | `salamander_snare2_hit_main_vl03_rr1.wav` |
| `OH/snare2_OH_F_10.wav` | `salamander_snare2_hit_main_vl03_rr10.wav` |
| `OH/snare2_OH_F_11.wav` | `salamander_snare2_hit_main_vl03_rr11.wav` |
| `OH/snare2_OH_F_12.wav` | `salamander_snare2_hit_main_vl03_rr12.wav` |
| `OH/snare2_OH_F_2.wav` | `salamander_snare2_hit_main_vl03_rr2.wav` |
| `OH/snare2_OH_F_3.wav` | `salamander_snare2_hit_main_vl03_rr3.wav` |
| `OH/snare2_OH_F_4.wav` | `salamander_snare2_hit_main_vl03_rr4.wav` |
| `OH/snare2_OH_F_5.wav` | `salamander_snare2_hit_main_vl03_rr5.wav` |
| `OH/snare2_OH_F_6.wav` | `salamander_snare2_hit_main_vl03_rr6.wav` |
| `OH/snare2_OH_F_7.wav` | `salamander_snare2_hit_main_vl03_rr7.wav` |
| `OH/snare2_OH_F_8.wav` | `salamander_snare2_hit_main_vl03_rr8.wav` |
| `OH/snare2_OH_F_9.wav` | `salamander_snare2_hit_main_vl03_rr9.wav` |
| `OH/snare2_OH_FF_1.wav` | `salamander_snare2_hit_main_vl04_rr1.wav` |
| `OH/snare2_OH_FF_2.wav` | `salamander_snare2_hit_main_vl04_rr2.wav` |
| `OH/snare2_OH_FF_3.wav` | `salamander_snare2_hit_main_vl04_rr3.wav` |
| `OH/snare2_OH_FF_4.wav` | `salamander_snare2_hit_main_vl04_rr4.wav` |
| `OH/snare2_OH_FF_5.wav` | `salamander_snare2_hit_main_vl04_rr5.wav` |
| `OH/snare2_OH_FF_6.wav` | `salamander_snare2_hit_main_vl04_rr6.wav` |
| `OH/snare2_OH_FF_7.wav` | `salamander_snare2_hit_main_vl04_rr7.wav` |
| `OH/snare2_OH_FF_8.wav` | `salamander_snare2_hit_main_vl04_rr8.wav` |
| `OH/snare2OFF_OH_P_1.wav` | `salamander_snare2_mute_main_vl01_rr1.wav` |
| `OH/snare2OFF_OH_P_2.wav` | `salamander_snare2_mute_main_vl01_rr2.wav` |
| `OH/snare2OFF_OH_P_3.wav` | `salamander_snare2_mute_main_vl01_rr3.wav` |
| `OH/snare2OFF_OH_P_4.wav` | `salamander_snare2_mute_main_vl01_rr4.wav` |
| `OH/snare2OFF_OH_P_5.wav` | `salamander_snare2_mute_main_vl01_rr5.wav` |
| `OH/snare2OFF_OH_P_6.wav` | `salamander_snare2_mute_main_vl01_rr6.wav` |
| `OH/snare2OFF_OH_F_1.wav` | `salamander_snare2_mute_main_vl02_rr1.wav` |
| `OH/snare2OFF_OH_F_10.wav` | `salamander_snare2_mute_main_vl02_rr10.wav` |
| `OH/snare2OFF_OH_F_2.wav` | `salamander_snare2_mute_main_vl02_rr2.wav` |
| `OH/snare2OFF_OH_F_3.wav` | `salamander_snare2_mute_main_vl02_rr3.wav` |
| `OH/snare2OFF_OH_F_4.wav` | `salamander_snare2_mute_main_vl02_rr4.wav` |
| `OH/snare2OFF_OH_F_5.wav` | `salamander_snare2_mute_main_vl02_rr5.wav` |
| `OH/snare2OFF_OH_F_6.wav` | `salamander_snare2_mute_main_vl02_rr6.wav` |
| `OH/snare2OFF_OH_F_7.wav` | `salamander_snare2_mute_main_vl02_rr7.wav` |
| `OH/snare2OFF_OH_F_8.wav` | `salamander_snare2_mute_main_vl02_rr8.wav` |
| `OH/snare2OFF_OH_F_9.wav` | `salamander_snare2_mute_main_vl02_rr9.wav` |
| `OH/splash1_OH_P_1.wav` | `salamander_splash1_hit_main_vl01_rr1.wav` |
| `OH/splash1_OH_P_2.wav` | `salamander_splash1_hit_main_vl01_rr2.wav` |
| `OH/splash1_OH_P_3.wav` | `salamander_splash1_hit_main_vl01_rr3.wav` |
| `OH/splash1_OH_P_4.wav` | `salamander_splash1_hit_main_vl01_rr4.wav` |
| `OH/splash1_OH_P_5.wav` | `salamander_splash1_hit_main_vl01_rr5.wav` |
| `OH/splash1_OH_F_1.wav` | `salamander_splash1_hit_main_vl02_rr1.wav` |
| `OH/splash1_OH_F_2.wav` | `salamander_splash1_hit_main_vl02_rr2.wav` |
| `OH/splash1_OH_F_3.wav` | `salamander_splash1_hit_main_vl02_rr3.wav` |
| `OH/splash1_OH_F_4.wav` | `salamander_splash1_hit_main_vl02_rr4.wav` |
| `OH/splash1_OH_F_5.wav` | `salamander_splash1_hit_main_vl02_rr5.wav` |
| `OH/hiTom_OH_P_1.wav` | `salamander_tom1_hit_main_vl01_rr1.wav` |
| `OH/hiTom_OH_P_2.wav` | `salamander_tom1_hit_main_vl01_rr2.wav` |
| `OH/hiTom_OH_P_3.wav` | `salamander_tom1_hit_main_vl01_rr3.wav` |
| `OH/hiTom_OH_P_4.wav` | `salamander_tom1_hit_main_vl01_rr4.wav` |
| `OH/hiTom_OH_P_5.wav` | `salamander_tom1_hit_main_vl01_rr5.wav` |
| `OH/hiTom_OH_P_6.wav` | `salamander_tom1_hit_main_vl01_rr6.wav` |
| `OH/hiTom_OH_P_7.wav` | `salamander_tom1_hit_main_vl01_rr7.wav` |
| `OH/hiTom_OH_P_8.wav` | `salamander_tom1_hit_main_vl01_rr8.wav` |
| `OH/hiTom_OH_P_9.wav` | `salamander_tom1_hit_main_vl01_rr9.wav` |
| `OH/hiTom_OH_F_1.wav` | `salamander_tom1_hit_main_vl02_rr1.wav` |
| `OH/hiTom_OH_F_10.wav` | `salamander_tom1_hit_main_vl02_rr10.wav` |
| `OH/hiTom_OH_F_2.wav` | `salamander_tom1_hit_main_vl02_rr2.wav` |
| `OH/hiTom_OH_F_3.wav` | `salamander_tom1_hit_main_vl02_rr3.wav` |
| `OH/hiTom_OH_F_4.wav` | `salamander_tom1_hit_main_vl02_rr4.wav` |
| `OH/hiTom_OH_F_5.wav` | `salamander_tom1_hit_main_vl02_rr5.wav` |
| `OH/hiTom_OH_F_6.wav` | `salamander_tom1_hit_main_vl02_rr6.wav` |
| `OH/hiTom_OH_F_7.wav` | `salamander_tom1_hit_main_vl02_rr7.wav` |
| `OH/hiTom_OH_F_8.wav` | `salamander_tom1_hit_main_vl02_rr8.wav` |
| `OH/hiTom_OH_F_9.wav` | `salamander_tom1_hit_main_vl02_rr9.wav` |
| `OH/hiTom_OH_FF_1.wav` | `salamander_tom1_hit_main_vl03_rr1.wav` |
| `OH/hiTom_OH_FF_10.wav` | `salamander_tom1_hit_main_vl03_rr10.wav` |
| `OH/hiTom_OH_FF_11.wav` | `salamander_tom1_hit_main_vl03_rr11.wav` |
| `OH/hiTom_OH_FF_12.wav` | `salamander_tom1_hit_main_vl03_rr12.wav` |
| `OH/hiTom_OH_FF_2.wav` | `salamander_tom1_hit_main_vl03_rr2.wav` |
| `OH/hiTom_OH_FF_3.wav` | `salamander_tom1_hit_main_vl03_rr3.wav` |
| `OH/hiTom_OH_FF_4.wav` | `salamander_tom1_hit_main_vl03_rr4.wav` |
| `OH/hiTom_OH_FF_5.wav` | `salamander_tom1_hit_main_vl03_rr5.wav` |
| `OH/hiTom_OH_FF_6.wav` | `salamander_tom1_hit_main_vl03_rr6.wav` |
| `OH/hiTom_OH_FF_7.wav` | `salamander_tom1_hit_main_vl03_rr7.wav` |
| `OH/hiTom_OH_FF_8.wav` | `salamander_tom1_hit_main_vl03_rr8.wav` |
| `OH/hiTom_OH_FF_9.wav` | `salamander_tom1_hit_main_vl03_rr9.wav` |
| `OH/loTom_OH_PP_1.wav` | `salamander_tom2_hit_main_vl01_rr1.wav` |
| `OH/loTom_OH_PP_2.wav` | `salamander_tom2_hit_main_vl01_rr2.wav` |
| `OH/loTom_OH_PP_3.wav` | `salamander_tom2_hit_main_vl01_rr3.wav` |
| `OH/loTom_OH_PP_4.wav` | `salamander_tom2_hit_main_vl01_rr4.wav` |
| `OH/loTom_OH_PP_5.wav` | `salamander_tom2_hit_main_vl01_rr5.wav` |
| `OH/loTom_OH_PP_6.wav` | `salamander_tom2_hit_main_vl01_rr6.wav` |
| `OH/loTom_OH_MP_1.wav` | `salamander_tom2_hit_main_vl02_rr1.wav` |
| `OH/loTom_OH_MP_10.wav` | `salamander_tom2_hit_main_vl02_rr10.wav` |
| `OH/loTom_OH_MP_2.wav` | `salamander_tom2_hit_main_vl02_rr2.wav` |
| `OH/loTom_OH_MP_3.wav` | `salamander_tom2_hit_main_vl02_rr3.wav` |
| `OH/loTom_OH_MP_4.wav` | `salamander_tom2_hit_main_vl02_rr4.wav` |
| `OH/loTom_OH_MP_5.wav` | `salamander_tom2_hit_main_vl02_rr5.wav` |
| `OH/loTom_OH_MP_6.wav` | `salamander_tom2_hit_main_vl02_rr6.wav` |
| `OH/loTom_OH_MP_7.wav` | `salamander_tom2_hit_main_vl02_rr7.wav` |
| `OH/loTom_OH_MP_8.wav` | `salamander_tom2_hit_main_vl02_rr8.wav` |
| `OH/loTom_OH_MP_9.wav` | `salamander_tom2_hit_main_vl02_rr9.wav` |
| `OH/loTom_OH_FF_1.wav` | `salamander_tom2_hit_main_vl03_rr1.wav` |
| `OH/loTom_OH_FF_2.wav` | `salamander_tom2_hit_main_vl03_rr2.wav` |
| `OH/loTom_OH_FF_3.wav` | `salamander_tom2_hit_main_vl03_rr3.wav` |
| `OH/loTom_OH_FF_4.wav` | `salamander_tom2_hit_main_vl03_rr4.wav` |
| `OH/loTom_OH_FF_5.wav` | `salamander_tom2_hit_main_vl03_rr5.wav` |
| `OH/loTom_OH_FF_6.wav` | `salamander_tom2_hit_main_vl03_rr6.wav` |
| `OH/loTom_OH_FF_7.wav` | `salamander_tom2_hit_main_vl03_rr7.wav` |
| `OH/loTom_OH_FF_8.wav` | `salamander_tom2_hit_main_vl03_rr8.wav` |

</details>

## How it was made

The upstream WAV bytes were copied and renamed only. No audio was resampled, normalized or trimmed. Each Opus twin was encoded from its unchanged source with:

```sh
opusenc --bitrate 160 --vbr --comp 10 --framesize 20 "<source>" "opus/<stem>.opus"
```

Encoding used `opusenc` from opus-tools 0.2 (libopus 1.6.1). `opusenc` resamples to 48 kHz; that is the only processing applied, and it happens in the Opus twin, not in `source/`.

## Removal

To request removal, open an issue at <https://github.com/michalslonina/drum-samples-salamander/issues> or contact the author at `axeldenstore (at) gmail (dot) com`; removal is immediate.
