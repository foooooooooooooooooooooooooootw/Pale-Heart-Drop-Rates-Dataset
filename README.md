# Pale Heart Drop Rates Dataset
<p>A dataset I decided to put together while farming.</p>
<br></br>
<p>Destiny 2 is a game where the developers like obscuring the numbers behind, well - everything. I figured it would be interesting for data exploration, as well as for finding any hidden correlations between variables (which I already have suspicions about). I intend to upload my findings after I have gathered more data points, especially because some of the rates are so low. I did not use any macros to farm these, and it's been a one man job. </p>

# Table of contents
1. [Dataset Information](#Dataset)
2. [Analysis & Insights](#Analysis)
3. [Postscript](#Postscript)

## Dataset <a name="Dataset"></a>

<p> There are two datasets, both comma seperated values (csv) files. PHDRC.csv consists of 8 columns/variables and outlines drops for chests opened in the pale heart. PHDRS.csv consists of 4 columns/variables and outlines drops for stigmata of the witness. The dataset should be skewed towards earlier overthrow levels simply because it always starts from 1. It was encoded in the Western Europe Windows 1251/WinLatin 1 character set but it seems to open fine in UTF-8. </p>

### PHDRC.csv
| Variable  | Details |
| ------------- | ------------- |
| Glimmer  | The amount of in game glimmer currency obtained from opening the chest. A numeric variable which I believe is discrete. These values are after applying a 65% glimmer boost from the ghost mod. One thing to note is that I believe there is some sort of internal rounding because manually multiplying the base values by 1.65x gives a slightly different number. |
| PHE  | Short for "Pale Heart Engram". A type of drop that can be obtained by opening a chest only on the Pale Heart. Originally binary, one time two of them dropped from the same chest. You might exclude that entry to turn it binary.  |
| GE  | Short for "Gunsmith Engram".  A type of drop that can be obtained by opening a chest but also drops everywhere in the system. This field might be influenced by drops obtained not on the pale heart.|
| CI  | Short for "Class Item". It refers to the exotic class items (Solipsism, Relativism, Stoicism). A binary field where a 1 denotes a drop.  |
| Mod  | Whether a mod that can be used on the traveler was obtained. A binary field where a 1 denotes a drop.  |
| Type  | The type of chest that was opened. "WC" stands for "World Chest", "HVT" stands for "High Value Target", "AB" stands for Area Boss and "EC" stands for "Encounter Chest". HVT are roaming bosses that may be named or unnamed. Area Bosses are typically named and are referred to in the pathfinder. |
| OL  | Short for "Overthrow Level". The level of the overthrow event at which the chest was opened. Overthrow levels from 1-3 correspond to their in-game level, while OL 4 is the boss phase and OL 5 is the intermission period after the boss is defeated.  |
| AO  | Short for "Area of Overthrow". There's only three which correspond to the in game areas.  |

### PHDRS.csv
| Variable  | Details |
| ------------- | ------------- |
| Glimmer  | The amount of in game glimmer currency obtained from opening the chest. A numeric variable which I believe is discrete. These values are after applying a 65% glimmer boost from the ghost mod. One thing to note is that I believe there is some sort of internal rounding because manually multiplying the base values by 1.65x gives a slightly different number. |
| ~~PHE~~  | ~~Short for "Pale Heart Engram". A type of drop that can be obtained by opening a chest only on the Pale Heart.~~ I could've sworn I'd received at least one from a stigma before... but after 300+ data points without getting one I must've hallucinated it  |
| Mod  | Whether a mod that can be used on the traveler was obtained. A binary field where a 1 denotes a drop.  |
| OL  | Short for "Overthrow Level". The level of the overthrow event at which the chest was opened. Overthrow levels from 1-3 correspond to their in-game level, while OL 4 is the boss phase and OL 5 is the intermission period after the boss is defeated.  |
| AO  | Short for "Area of Overthrow". There's only three which correspond to the in game areas.  |

## Analysis & Insights <a name="Analysis"></a>

Analysis will be attached here.

## Postscript <a name="Postscript"></a>

To note, since there has been <a href="https://www.bungie.net/7/en/News/article/twid-07-25-2024">an announcement</a> that drop rates from chests are going to be reduced, a separate dataset will be created post August patch. 

I also intend to create a dataset that includes all class item perk combinations in order to check if the rolls are weighted, as well as perk/frame combinations for ergo sum to see if those are weighted as well. 

On 5 August's commit, I added about 200 entries, hitting 1000 rows. I also realized I made a terrible mistake as my gunsmith engrams were full, meaning I did not get any for about 200 entries. At least gunsmith engrams are not pale heart related, so I think it's not an issue. On the older dataset, the percentage of a gunsmith engram dropping was about 17.07%.

