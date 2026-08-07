# Changelog

All notable changes to this mod, derived from the git history.

## Season 14 (main, in progress)

- Added the `KvaszUnique` decision/on_action pack, including a "give up hegemony" decision that removes hegemon status (with a `lost_hegemony` penalty modifier) and an infrastructure-expansion tracking decision. (`6615bd7f`)
- Added a new "Cloves Abundance" trade goods event that permanently drops the price of cloves once Sarhal's clove production is high enough, and lowered cloves' base price (8 → 5). (`6615bd7f`)
- Reworked several Magocracy idea group bonuses: swapped `mages_loyalty_modifier`/`global_tax_modifier`/`improve_relation_modifier` bonuses out for mana-regen, mage estate/ruler experience, magical infrastructure bypass, hostile attrition, and diplomatic reputation effects. (`6615bd7f`)
- Rebalanced misc. ideas/policies: Humanist ideas gain `-5%` global autonomy, Fahvanosy's ideas swapped a naval morale/dev cost bonus for navy morale recovery speed/build time, `eight_schools_of_magic` policy traded prestige for diplomatic reputation and same-culture relations, and `tactful_tactics` policy traded diplomatic reputation for cheaper diplomatic annexation. (`6615bd7f`)
- Nerfed the Avo-Nakavy deity Drongray: swapped its naval engagement bonus for a ship recruit speed penalty (kept the naval attrition reduction). (`6615bd7f`)

## Season 13

- Renamed country A79 from "Gnomish Hierarchy" to "Oddansbay Hierarchy" and updated its flag, as a seasonal cosmetic refresh. (`81c0465f`)
- Made the AI unable to declare or join a League War (added `ai = no` to the religious league CB and to the league-enemy join trigger), so only players can start/join them. (`37f67aad`, `d02efd28`)
- Rebalanced climate static modifiers: arctic has slower colonization (-10 → -30), more supply, and no building-slot penalty; arctic/arid development cost cut further. (`5962bb3e`)
- Disabled the hold `no_subterannean_race` penalty modifier so all races can make full use of holds, fixed a typo that stopped the Regent Court's infantry power ICA bonus from applying (was `infatry_power`), and gated the Umbral Covenant formable decision behind the year 1525. (`fdefbce3`)
- Cannorian religion changes (`652ad468`, `f41675ce`):
    - replaced Corinite's 3.5% discipline bonus with 0.5 army tradition
    - swapped the Regent Court's 2% heathen tolerance bonus for 5% infantry power ICA (later fixed by the typo patch above)
    - tripled the mana cost of Ravelian's `use_warrior_automata` ability (50 → 150) and removed the 10% morale buff from `papal_blessing` (`6bfe802d`)
- Halved Old Dookan's "guidance of peace" development cost reduction (-20% → -10%). (`da13b3cb`)
- Moved the Ynnic Adventurer origin provinces: Argezvale now spawns from Rubyhold instead of Redfort, and the House of Reflection/Elfrealm of Elathael now spawns from Ibevar instead of Silent Repose. (`6f6b75a2`)
- Major systems rework (`984e61d0`):
    - Overhauled army professionalism into a new custom rank system (`common/professionalism/00_modifiers.txt`)
    - Added a large set of new admin/military policies (`common/policies/00_adm.txt`, expanded `00_mil.txt`) and removed a couple of redundant diplomatic policies (`professional_diplomatic_corps`, `the_integrated_administration_act`)
    - Added Artificer/Magocracy idea group icons
    - Fully removed the no-subterranean-race penalty and its old centaur-horde-reform exception
    - Re-gated Naval Ideas behind the year 1800 instead of disabling the group outright (superseding the full disable from `0d58ff28` below)
    - Rebalanced dozens of basic idea group bonuses (buffs and nerfs), e.g. Religious Tradition's same-religion opinion bonus (+10 → +25) and spy cost reduction (-20% → -25%) in exchange for losing yearly corruption reduction, Foreign Embassies' advisor cost discount deepened (-25% → -33%), National Conscripts' recruit speed bonus deepened (-10% → -25%), Glorious Arms swapped prestige-from-land for a cannon count bonus, Cultural Ties' accepted cultures doubled (2 → 4), and Expanded Contracts' mercenary maintenance discount halved (-25% → -10%) in exchange for a matching naval maintenance discount
- Removed a -10% development cost bonus from Giberd's Civil Engineering Academy idea to bring it in line with the same nerf already applied to Nimscodd. (`4a3c19af`, `8feae939`)
- Trimmed a broken opinion/spy-network requirement out of a Hytiranyalen mission's trigger. (`4f797107`)
- Gave Corvuria a proper map color (grey → maroon) instead of the generic placeholder, purely cosmetic and unvoted-on ("from Friday mod"). (`93745b9d`)
- Removed the 30-day grace period before anyone can declare war, so day-zero declarations are now allowed. (`9c1cc965`)
- Fixed a crash in the Ruined Sea trade node caused by a duplicated/broken `outgoing` trade path and duplicate `members` block (a copy-paste artifact of the new "moduk" trade path added back in `3c7fdf09`). (`92b65d72`)
- General balance/feedback pass: made hired mercenary manpower recover 3x slower, disabled the naval ideas group entirely, removed a "SUBMOD - easier than changing tech" ADM/DIP power grant from the Mulen flavour event, and fixed racial localisation text. (`0d58ff28`)
- Bundled "last-minute" changes (`622113c5`):
    - Added the `sloots` event chain and a large passive "demonsterization" event system letting monstrous-race provinces be converted/assimilated over time
    - Added an escalating naval-forcelimit-overflow penalty: exceeding your naval force limit now stacks increasing `sailors_recovery_speed` penalties (up to -100%) via a new automated on_action check
    - Added tiered condottieri availability by government type (despotic/reformed/absolutist/revolutionary monarchies get progressively more available condottieri)
    - Opened the vampire estate's spread ability to any culture/location for AI countries, removing the human/half-elf-only and Europe-only restrictions ("in our submod ANYONE can be a vampire")
    - Nerfed several magic modifiers: Combat Ward lost its dice-roll bonus for a smaller shock-damage-received reduction, Manipulated Fortune lost its dice-roll bonus for a discipline bonus, and Foresight now carries a small development cost penalty
    - Swapped several "requires Manufactories institution" triggers (the Rise of Artificery incident, the artifice system setup) to "requires Global Trade institution," unlocking them roughly 50 years earlier
    - Reworked the `artificed_defenses` policy (traded its anti-fort artillery bonus for hostile attrition + fort maintenance reduction) and removed the manpower-granting effect from the "The Draft" parliament issue
    - Removed the extra `artificers_capacity`/`cavalry_power` bonuses from upgraded tiers of the Toncodden Lighthouse and Lorenan's Rest monuments, excluded Harpy Matriarchy reform from losing the monstrous tribe estate
    - Rate-limited army professionalism gain from recruiting generals to once every 120 days starting in 1550
    - Removed the historical Elizna-Drolakand vassalage and Tiltwick's B07 starting ownership/core, and halved a devil-summon backline fire damage bonus (+15% → +7.5%)
- Restored a large block of previously disabled Karakhanbar (Z54) content — mission trees, decisions, and flavour events across `Flavour_Karakhanbar_Z54.txt`, `Karakhanbar_Missions.txt`, `DeepwoodsEvents.txt`, `Flavour_ShatteredCrown_H72.txt`, `countrydecisionsview.txt`, and its on_action event manager — that had been commented out with `always = no # Karakhanbar Comment Out`. (`0a59954b`)
- Also in that pass: limited the Artificers estate's "draft artificers" decision to once per game via a country flag, expanded the map-shrinking settings option to also delete the Gozengun, East Serpentspine, Yanshen, Vimdatrong, Forbidden Lands, Kheionai, and Rahen superregions, added the Monstrous Decisions decision file, raised the Hoard Curse disaster's development threshold twelvefold (600 → 6000, making it far rarer), added tag Z55 to the artificery-only-mode allow-list, softened an Eborthil mission's forced alliance into a historical friendship, and gave rulers with the Council of Mages idea extra weight toward Powerful Mage heir/bastard events. (`0a59954b`)

## Season 12/Earlier

- Baseline rebalance pass (`3c7fdf09`):
    - significantly reduced manpower bonuses from Barracks/Training Fields/Soldier Households
    - reduced base manpower per dev from 250 to 200
    - halved bonus from forcelimit buildings (land and naval)
    - gave Mage Towers +1 max attrition
    - doubled ticking-warscore gain and its cap
    - reduced mercenary manpower reserves to 2/3 of vanilla
    - reduced mercenary recovery rate while hired from 1/2 to 1/3
    - enabled the "monstrous rule" age ability for all monstrous nations (previously limited to a hardcoded culture list)
    - halved the Age of Reformation's ship-cost discount age ability (-50% → -25%)
    - fixed the parliament "pay stability" bribe to a flat -1 stability cost
    - removed development cost from the church's "inwards perfection" estate privilege
    - removed mercenary discipline from adventurers estate loyalty and halved mercenary cost
    - removed the elven military's manpower recovery penalty by a third (-50% → -33%) and removed the orcish administration's +10% development cost penalty
    - reworked human minority/majority population modifiers: replaced their local development cost discount with a local production efficiency bonus and boosted their manpower bonus
    - removed the ADM/DIP/MIL mana cost for repairing ruined/damaged holds entirely (previously scaled up to -500 each at 100 development)
    - swapped the Technocracy republic reform's institution requirement from Manufactories to Global Trade, unlocking it earlier
    - disabled the Khetist "aakhet's rage" blessing
    - replaced the Encourage Development state edict's -10% development cost bonus with -33% local monthly devastation
    - added +1% yearly army professionalism to the Army Tradition static modifier
    - added new "moduk" and "clovesight" outgoing trade paths to the Ruined Sea and Banished Isles trade nodes
    - adjusted "The Command" event's AI option weights to consistently favor the "stay loyal" outcome
    - gated a hidden Halessi Spirits rending event behind the year 1600 and shortened its mean-time-to-happen from 50 years to 1
    - reworked A79's national ideas to match Nimscodd's dev-cost-to-build-cost and artillery-to-land-attrition/defensiveness nerfs, and nerfed several of R72 (Dhugajir)'s cavalry bonuses
- Imported the Anbennar Insyaa base mod as the starting point for this fork. (`ba87cb9d`)
