# Pale Heart Drop Rates Dataset
<p>A dataset I decided to put together while farming.</p>
<br></br>
<p>Destiny 2 is a game where the developers like obscuring the numbers behind, well - everything. I figured it would be interesting for data exploration, as well as for finding any hidden correlations between variables (which I already have suspicions about). I intend to upload my findings after I have gathered more data points, especially because some of the rates are so low. I did not use any macros to farm these, and it's been a one man job. </p>

# Table of contents
1. [Dataset Information](#Dataset)
2. [Exploratory Data Analysis](#Exploration)
3. [Analysis & Insights](#Analysis)
    1. [Pre-August 7th](#analysis1)
    2. [Post-August 7th](#analysis2)
5. [Postscript](#Postscript)

## Dataset <a name="Dataset"></a>

<p> There are two datasets, both comma seperated values (csv) files. PHDRC.csv consists of 8 columns/variables and outlines drops for chests opened in the pale heart. PHDRS.csv consists of 4 columns/variables and outlines drops for stigmata of the witness. The dataset should be skewed towards earlier overthrow levels simply because it always starts from 1. It is encoded in UTF-8. </p>

<p> 2 more will be added after August 7th's patch. Although I think there should be no difference for the stigmata, I'll separate them anyway. The new dataset, PHDRC78.csv consists of more columns than its predecessor, now including legendary drops and the "subtype" of encounters and HVT. </p>

### PHDRC.csv
| Variable  | Details |
| ------------- | ------------- |
| Glimmer  | The amount of in game glimmer currency obtained from opening the chest. A numeric variable which I believe is discrete. These values are after applying a 65% glimmer boost from the ghost mod. One thing to note is that I believe there is some sort of internal rounding because manually multiplying the base values by 1.65x gives a slightly different number. |
| PHE  | Short for "Pale Heart Engram". A type of drop that can be obtained by opening a chest only on the Pale Heart. Binary.  |
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

### PHDRC78.csv
| Variable  | Details |
| ------------- | ------------- |
| Glimmer  | The amount of in game glimmer currency obtained from opening the chest. A numeric variable which I believe is discrete. These values are after applying a 65% glimmer boost from the ghost mod. One thing to note is that I believe there is some sort of internal rounding because manually multiplying the base values by 1.65x gives a slightly different number. |
| PHE  | Short for "Pale Heart Engram". A type of drop that can be obtained by opening a chest only on the Pale Heart. Binary.  |
| GE  | Short for "Gunsmith Engram".  A type of drop that can be obtained by opening a chest but also drops everywhere in the system. This field might be influenced by drops obtained not on the pale heart.|
| CI  | Short for "Class Item". It refers to the exotic class items (Solipsism, Relativism, Stoicism). A binary field where a 1 denotes a drop.  |
| Mod  | Whether a mod that can be used on the traveler was obtained. A binary field where a 1 denotes a drop.  |
| LI  | Short for "Legendary Item". Any Legendary gear that drops from a chest. May be more than 1 so this is not a binary field.  |
| Type  | The type of chest that was opened. "WC" stands for "World Chest", "HVT" stands for "High Value Target", "AB" stands for Area Boss and "EC" stands for "Encounter Chest". HVT are roaming bosses that may be named or unnamed. Area Bosses are typically named and are referred to in the pathfinder. |
| Subtype  | The subtype of encounter or name of HVT. Subtypes of encounters are like "Stitching" or "Offering". Not all encounters are named. |
| OL  | Short for "Overthrow Level". The level of the overthrow event at which the chest was opened. Overthrow levels from 1-3 correspond to their in-game level, while OL 4 is the boss phase and OL 5 is the intermission period after the boss is defeated.  |
| AO  | Short for "Area of Overthrow". There's only three which correspond to the in game areas.  |

## Exploratory Data Analysis <a name="Exploration"></a>
### PHDRC.csv
The dataset is heavily skewed towards world chests, which is expected since world chests are much more abundant than any other type of chest.

<img title="chest distribution" src="https://github.com/foooooooooooooooooooooooooootw/Pale-Heart-Drop-Rates-Dataset/blob/main/res/chest%20distribution.png">

The dataset is also skewed towards the left for overthrow levels.

<img title="overthrow distribution" src="https://github.com/foooooooooooooooooooooooooootw/Pale-Heart-Drop-Rates-Dataset/blob/main/res/level%20distribution.png">

Finally, the dataset has the most chests opened in the blooming, while the amount of chests in the landing and impasse are about the same.

<img title="area distribution" src="https://github.com/foooooooooooooooooooooooooootw/Pale-Heart-Drop-Rates-Dataset/blob/main/res/area%20distribution.png">

### PHDRS.csv

Similar to the above dataset, this dataset is skewed left for overthrow levels and most stigmata are picked up in the blooming.

<img title="overthrow distribution" src="https://github.com/foooooooooooooooooooooooooootw/Pale-Heart-Drop-Rates-Dataset/blob/main/res/stigmata%20level%20distribution.png">
<img title="overthrow distribution" src="https://github.com/foooooooooooooooooooooooooootw/Pale-Heart-Drop-Rates-Dataset/blob/main/res/stigma%20area%20distribution.png">

## Analysis & Insights <a name="Analysis"></a>

## Pre-August 7th patch <a name="analysis1"></a>

### PHDRC.csv
### At a glance

- Overall, 69.95% of the time when you open a chest, you get nothing but glimmer.
- Overall, pale heart engrams drop at a 9.1% chance.
- Overall, gunsmith engrams are almost double the drop rate of pale heart engrams, at 17.07%.
- Overall, class items drop at about 2.6% chance.
- Overall, there is a 5.1% chance of getting a mod.

### Glimmer drop rates compared

Glimmer amounts are discrete as shown in the notebook. Regardless, this is the distribution:

<img title="chest distribution" src="https://github.com/foooooooooooooooooooooooooootw/Pale-Heart-Drop-Rates-Dataset/blob/main/res/glimmer%20distribution.png">

The median is 660, the mode is 693 & the mean is 575.

| Glimmer Amounts  | Drop Rates |
| ------------- | ------------- |
| 693 | 26.8% |
| 660  | 18.1% |
| 726  | 15.1%  |
| 264  | 11.2% |
| 231 | 6.4% |
| 495  | 5.8%  |
| 297  | 5.4%  |
| 627  | 4%  |
| 759 | 3.5% |
| 330 | 0.8%  |
| 825  | 0.8%  |
| 528 | 0.7%  |
| 462  | 0.5%  |
| 792  | 0.4%  |
| 0  | 0.3%  |
| 497  | 0.1% |
| 315  | 0.1% |

Generally, you'd have a 68.7% of getting an amount above the mean. 

### Pale Heart Engram drop rates compared
| Category  | Drop Rates |
| ------------- | ------------- |
| Overall | 9.2% |
|  |  |
| World Chests  | 8.676% |
| Encounter Chests  | 15.385%  |
| HVT Chests  |  7.018% |
|  |  |
| The Landing  | 8.974%  |
| The Blooming  | 9.075%  |
| The Impasse  | 9.314%  |
|  |  |
| Overthrow Level 1 | 10.682%  |
| Overthrow Level 2  | 7.258%  |
| Overthrow Level 3 | 12.255%  |
| Overthrow Level 4  | 5.0%  |
| Overthrow Level 5  | 6.593%  |

As you can see, encounter chests have a much higher chance of dropping a pale heart engram, and HVT has the worst. The Impasse also seems like a place that is most likely to drop one, although it may be tied to the amount of encounters I did in the Impasse. Similar to Overthrow level 3, the drop rates are twice that of overthrow level 4 - but it might be because more encounters were done in 3 than 4.

### Class Item drop rates compared
| Category  | Drop Rates |
| ------------- | ------------- |
| Overall | 2.6% |
|  |  |
| World Chests  | 2.511% |
| Encounter Chests  | 3.077%  |
| HVT Chests  |  3.509% |
|  |  |
| The Landing  | 2.564%  |
| The Blooming  | 2.669%  |
| The Impasse  | 2.451%  |
|  |  |
| Overthrow Level 1 | 2.077%  |
| Overthrow Level 2  | 2.419%  |
| Overthrow Level 3 | 3.431%  |
| Overthrow Level 4  | 3.333%  |
| Overthrow Level 5  | 2.198%  |

It seems to drop the most often from HVT and encounter chests, but those numbers pale in comparison to the amount of world chests opened. Of course, there is a good possibility that it is higher than the world chests since they're considered "harder", as seen from points gained when completing either objective. Somehow, Overthrow level 3 is also the highest of all the overthrow levels. The drop chance seems to vary since at 1000 chests opened I have a 2.6% drop chance but a friend I know has opened 6800 chests but has a 1.87% drop rate.

### Mod drop rates compared
| Category  | Drop Rates |
| ------------- | ------------- |
| Overall | 5.1% |
|  |  |
| World Chests  | 3.539% |
| Encounter Chests  | 13.846%  |
| HVT Chests  |  19.298% |
|  |  |
| The Landing  | 3.846%  |
| The Blooming  | 5.516%  |
| The Impasse  | 5.392%  |
|  |  |
| Overthrow Level 1 | 6.825%  |
| Overthrow Level 2  | 6.048%  |
| Overthrow Level 3 | 3.431%  |
| Overthrow Level 4  | 5.0%  |
| Overthrow Level 5  |  0.0%  |

I have a sneaking suspicion that the more mods you get, the less likely it is to get more mods. Maybe getting all of them means you don't get any mods to drop if you would've gotten one, which can be seen in how the chances keep dropping per overthrow level (OL4 is the outlier?). It can also be seen that HVT chests have the highest chance to drop mods. 

### PHDRS.csv
### At a glance
- Overall, 97.37% of the time when you pick up a stigma, you get nothing but glimmer.
- Overall, chances of getting a mod from stigmata are 2.63% (about as rare as a class item?).
- The Impasse seems to have a higher expected value of glimmer as compared to the other areas.

### Glimmer Comparison
- The median is 745
- The mode is 910
- The mean is 822

Overall, these are the glimmer drop rates:

| Glimmer Amount | Drop Rates |
| ------------- | ------------- |
| 910 | 32.17% |
| 745 | 31.95% |
| 580 | 15.09% |
| 1075 | 14.55% |
| 415 | 3.61% |
| 1240 | 2.63% |

### Glimmer Comparison by Area

### The Landing
| Glimmer Amount | Drop Rates |
| ------------- | ------------- |
| 745 | 34.09% |
| 910 | 30.91% |
| 580 | 16.36% |
| 1075 | 14.55% |
| 415 | 2.27% |
| 1240 | 1.82% |

Expected Value = <ins>818.54</ins>


### The Blooming
| Glimmer Amount | Drop Rates |
| ------------- | ------------- |
| 910 | 33.54% |
| 745 | 31.31% |
| 580 | 15.15% |
| 1075 | 13.54% |
| 415 | 4.04% |
| 1240 | 2.42% |

Expected Value = <ins>818.67</ins>

### The Impasse
| Glimmer Amount | Drop Rates |
| ------------- | ------------- |
| 745 | 31.16% |
| 910 | 30.15% |
| 1075 | 17.09% |
| 580 | 13.57% |
| 415 | 4.02% |
| 1240 | 4.02% |

Expected Value = <ins>835.46</ins>

As you can see, the expected value of the Landing and the Blooming are within 0.13 glimmer of each other, while the Impasse has about 17 more glimmer than the other two. Perhaps farming glimmer from stigmata in the Impasse is more efficient.

## Post-August 7th patch <a name="analysis2"></a>
To be continued-

## Postscript <a name="Postscript"></a>

To note, since there has been <a href="https://www.bungie.net/7/en/News/article/twid-07-25-2024">an announcement</a> that drop rates from chests are going to be reduced, a separate dataset will be created post August patch. 

I also intend to create a dataset that includes all class item perk combinations in order to check if the rolls are weighted, as well as perk/frame combinations for ergo sum to see if those are weighted as well. 

On 5 August's commit, I added about 200 entries, hitting 1000 rows. I also realized I made a terrible mistake as my gunsmith engrams were full, meaning I did not get any for about 200 entries. At least gunsmith engrams are not pale heart related, so I think it's not an issue. On the older dataset, the percentage of a gunsmith engram dropping was about 17.07%. My preliminary investigation also showed no correlation between gunsmith engrams and the rest of the columns, so for now I will forget about them.

Another thing I realized - there is a bug where there is no rank up banner or reputation gauge for ghost, which coincidentally gives a pale heart engram. This might explain why sometimes I got more than 1 pale heart engram, or a pale heart engram from a stigma. I will correct for this issue in the newer version of the dataset.

