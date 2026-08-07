# Changelog

## Season 14 (main, in progress)
- reverted corvuria/gnomish hierarchy cosmetic changes
- Added Kvasz's unique decisions: a "give up hegemony" decision, an expand infrastructure tracking decision, and a dev click counter (`6615bd7f`)
- Added a new "Cloves Abundance" trade goods event that permanently drops the price of cloves once there are more than 5 cloves provinces, and lowered cloves' base price (8 → 5). (`6615bd7f`)
- Reworked Magocracy idea group bonuses: removed `mages_loyalty_modifier`/`global_tax_modifier`/`improve_relation_modifier` bonuses, added mana-regen, magical infrastructure bypass, hostile attrition, diplo rep, and max hostile attrition. (`6615bd7f`)
- Rebalanced misc. ideas/policies (`6615bd7f`): 
    - Humanist ideas: added -0.05 monthly autonomy to finisher
     - magocracy-humanist policy: changed +prestige to diplomatic reputation and same-culture relations
     - quality-influence policy: changed + dip rep for -annexation cost. 
- Fahvanosy nerfs (`6615bd7f`):
    - Fahvanosy's ideas: removed naval morale/dev cost bonus, added navy morale recovery speed, -build time
    - Nerfed Sarhalfling religion deity buff: changed global naval engagement to ship recruit speed penalty (kept the naval attrition reduction). 

## Season 13

- Renamed country A79 from "Gnomish Hierarchy" to "Oddansbay Hierarchy" and updated its flag, as a seasonal cosmetic refresh. (`81c0465f`)
- Made the AI unable to declare or join a League War (added `ai = no` to the religious league CB and to the league-enemy join trigger), so only players can start/join them. (`37f67aad`, `d02efd28`)
- Rebalanced climate static modifiers: arctic has slower colonization (-10 → -30), more supply, and no building-slot penalty, arctic/arid development penalty greatly reduced. (`5962bb3e`)
- Disabled the hold `no_subterannean_race` penalty modifier so all races can make full use of holds
- Gated Umbral Covenant formable decision behind the year 1525. (`fdefbce3`)
- Cannorian religion changes (`652ad468`, `f41675ce`): 
    - replaced Corinite's 3.5% discipline bonus with 0.5 army tradition
    - swapped the Regent Court's 2% heathen tolerance bonus for 5% infantry power ICA
    - tripled the cost of Ravelian's `use_warrior_automata` ability and removed the 10% morale buff 
- Orc dev cost rebalance: removed 10% dev cost penalty from orc admin, but halved Old Dookan's "guidance of peace" dev cost. (`da13b3cb`)
- moved Ynnic Adventurer spawn provinces: Argezvale now spawns from Rubyhold instead of Redfort, and the House of Reflection spawns from Ibevar instead of Silent Repose. (`6f6b75a2`)
- Overhauled army professionalism
- rebalanced policies, buffing underused combinations while nerfing common ideas (byebye qual-eco)
- Removed -10% dev cost from Giberd ideas (`4a3c19af`, `8feae939`)
- fixed broken opinion/spy-network requirement for Hytiranyalen mission. (`4f797107`)
- (Temp change) - Corvuria cosmetic color change. (`93745b9d`)
- Added day-zero war decs (`9c1cc965`)
- Monument nerfs (`622113c5`):
    - Removed the cavalry power bonus from Lorenan's Rest monument.
    - Removed artificer cap from toncodden lighthouse
- Re-enabled Karakhanbar's commented-out mission tree
- New Magic system rebalances:
    - combat ward changed from own_territory_dice_roll to -10% shock dmg received
    - halved local autonomy, manpower from field of forbiddence
    - changed manipulated fortune from attacker dice roll to discipline
    - added + dev cost from divination foresight (so its worse at devving)
    - nerfed lvl 3 conjuration cannon merc stack

## Season 12/Earlier
- Council of Mages (magocracy finisher) increases chance to roll the Powerful Mage personality (via chance or via getting mage heirs)
- Baseline rebalance pass (`3c7fdf09`): 
- significantly reduced manpower bonuses from Barracks/Training Fields/Soldier Households,
- reduced base manpower per dev from 250 to 200
- halved bonus from forcelimit buildings (land and naval), 
- gave Mage Towers +1 max attrition, 
- doubled ticking-warscore gain and its cap, 
- reduced mercenary manpower reserves to 2/3 of vanilla,
- reduced mercenary recovery rate while hired from 1/2 to 1/3
- enabled the "monstrous rule" age ability for all monstrous nations, 
- halved the Age of Reformation's ship-cost discount age ability (-50% → -25%), 
- fixed the parliament "pay stability" bribe to a flat -1 stability cost.
- removed development cost from "inwards perfection" estate privelege
- removed mercenary discipline from adventurers estate loyalty and halfed mercenary cost
- limited the Artificers estate's "draft artificers" decision to once per game via a country flag
- added passive monsterization to MonstrousDecisions  file (TODO: add the rest of the files necessary for this)
- enabled spreading vampires to non-human/half-elves
- added lobotomy event (`event sloots.0`)
- added increased condot amount modifier that increases each age
- added scaling sailor recovery nerf when over naval FL
- disabled naval ideas
- enabled artificery at global trade
- moved the rending to 1600
- nerfed Gnomish Hierarchy national ideas
- nerfed several Dhugajir cavalry bonuses
- trade rework to enable more trade flow from Aelentir to Haless/Sarhal
- replaced the Encourage Development state edict's -10% development cost bonus with -33% local monthly devastation
-  removed the elven military's manpower recovery penalty by a third (-50% → -33%) and removed the orcish administration's +10% development cost penalty
- reworked human minority/majority population modifiers: replaced their local development cost discount with a local production efficiency bonus and boosted their manpower bonus

- Imported the Anbennar Insyaa base mod as the starting point for this fork. (`ba87cb9d`)
