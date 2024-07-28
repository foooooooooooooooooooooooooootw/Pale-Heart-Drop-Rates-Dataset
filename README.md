# Pale Heart Drop Rates Dataset
<p>A dataset I decided to put together while farming.</p>
<br></br>
<p>Destiny 2 is a game where the developers like obscuring the numbers behind, well - everything. I figured it would be interesting for data exploration, as well as for finding any hidden correlations between variables (which I already have suspicions about). I intend to upload my findings after I have gathered more data points, especially because some of the rates are so low. I did not use any macros to farm these, and it's been a one man job. </p>

## Dataset

<p> There are two datasets, both comma seperated values (csv) files. PHDRC.csv consists of 8 columns/variables and outlines drops for chests opened in the pale heart. PHDRS.csv consists of 5 columns/variables and outlines drops for stigmata of the witness. It is encoded in the Western Europe Windows 1251/WinLatin 1 character set but it seems to open fine in UTF-8. </p>

### PHDRC.csv
| Variable  | Details |
| ------------- | ------------- |
| Glimmer  | The amount of in game glimmer currency obtained from opening the chest. A numeric variable which I believe is discrete.  |
| PHE  | Short for "Pale Heart Engram". A type of drop that can be obtained by opening a chest only on the Pale Heart. Originally binary, one time two of them dropped from the same chest. You might exclude that entry to turn it binary.  |
| GE  | Short for "Gunsmith Engram".  A type of drop that can be obtained by opening a chest but also drops everywhere in the system. This field might be influenced by drops obtained not on the pale heart.|
| CI  | Short for "Class Item". It refers to the exotic class items (Solipsism, Relativism, Stoicism). A binary field where a 1 denotes a drop.  |
| Mod  | Whether a mod that can be used on the traveler was obtained. A binary field where a 1 denotes a drop.  |
| Type  | The type of chest that was opened. "WC" stands for "World Chest", "HVT" stands for "High Value Target" and "EC" stands for "Encounter Chest".  |
| OL  | Short for "Overthrow Level". The level of the overthrow event at which the chest was opened. Overthrow levels from 1-3 correspond to their in-game level, while OL 4 is the boss phase and OL 5 is the intermission period after the boss is defeated.  |
| AO  | Short for "Area of Overthrow". There's only three which correspond to the in game areas.  |

### PHDRS.csv
| Variable  | Details |
| ------------- | ------------- |
| Glimmer  | The amount of in game glimmer currency obtained from opening the chest. A numeric variable which I believe is discrete.  |
| ~~PHE~~  | ~~Short for "Pale Heart Engram". A type of drop that can be obtained by opening a chest only on the Pale Heart.~~ I could've sworn I'd received at least one from a stigma before... but after 300+ data points without getting one I must've hallucinated it  |
| Mod  | Whether a mod that can be used on the traveler was obtained. A binary field where a 1 denotes a drop.  |
| OL  | Short for "Overthrow Level". The level of the overthrow event at which the chest was opened. Overthrow levels from 1-3 correspond to their in-game level, while OL 4 is the boss phase and OL 5 is the intermission period after the boss is defeated.  |
| AO  | Short for "Area of Overthrow". There's only three which correspond to the in game areas.  |

Analysis will be attached below in the future.

To note, since there has been <a href="https://www.bungie.net/7/en/News/article/twid-07-25-2024">an announcement</a> that drop rates from chests are going to be reduced, a separate dataset will be created post August patch. 

I also intend to create a dataset that includes all class item perk combinations in order to check if the rolls are weighted.
