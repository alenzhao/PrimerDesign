# PrimerDesign
RDP Primer Design Subcommands: Screen and Select

The main objective of the Primer Design program is to produce thermodynamically stable primer pairs from an input of aligned nucleotide sequences. The input nucleotide sequences should be in the FASTA format. 

Screen – command used to generate a graphical representation of the coverage and richness at each position of the reference set. A proportional bar graph of the theoretical uniform coverage is calculated at any given position as the summation of all possible targets hit divided by the total number of sequences. The richness at a particular position corresponds to the number of unique valid k-mers at that position.

Sample Screen Command
```
java -jar /path/to/PrimerDesign.jar -subcommand screen -input /path/to/refSequences.fasta -GraphOutput /path/to/userDir -oligoMinSize 15 -oligoMaxSize 30 -tempMin 55 -tempMax 63 -hairMax 35 -homoMax 35 -os mac -NoTEndFilter t -NoPoly3GCFilter t -PolyRunFilter 4 -GCFilterMin 0.45 -GCFilterMax 0.7 -assayMax 30 -degenMax 6 -sodiumConc 50.0 -magnesConc 1.5
```

Select – command that generates an output file of primer pairs with its corresponding target sequences. Initial program settings given by the user for the user’s record are also given as output. 

A user should consider the benefits of the insight from the screen results when running select. 

Perhaps there are high peaks of coverage slightly outside of the user’s initial desired amplicon product minimum and maximum lengths. The tag ‘IsSlidingScale’ can be set to ‘false’ to stop the generation of primer pairs from all positions with a sliding window. Then, set the forward and reverse minimum and maximum to position ranges that have high coverage and relatively moderate to low richness. 

Sample Select Command (without Sliding Scale)
```
java -jar /path/to/PrimerDesign.jar -subcommand select -input /path/to/refSequences.fasta -SlidingScale false -forwardMinPos 100 -forwardMaxPos 150 - reverseMinPos 425 -reverseMaxPos 450 -oligoMinSize 15 -oligoMaxSize 30 -maxMismatches 2 -tempMin 55 -tempMax 63 -hairMax 35 -homoMax 35 -isTreeWeightNeeded f -isHenikoffWeightNeeded t -os mac -output /work/leotift/nifHGrp2CmdLineResults -assayMax 30 -degenMax 6 -NoTEndFilter t -NoPoly3GCFilter t -PolyRunFilter 4 -GCFilterMin 0.45 -GCFilterMax 0.7 -sodiumConc 50.0 -magnesConc 1.5
```




Perhaps coverage does not vary significantly based upon position. This would be the time to just use the sliding window with a product length minimum and maximum.  

Sample Select Command (with Sliding Scale)
```
java -jar /path/to/PrimerDesign.jar -subcommand select -input /path/to/refSequences.fasta -SlidingScale true -productLengthMin 150 -productLengthMax 250 -oligoMinSize 15 -oligoMaxSize 30 -maxMismatches 2 -tempMin 55 -tempMax 63 -hairMax 35 -homoMax 35 -isTreeWeightNeeded f -isHenikoffWeightNeeded t -os mac -output /work/leotift/CmdLineResults -assayMax 30 -degenMax 6 -NoTEndFilter t -NoPoly3GCFilter t -PolyRunFilter 4 -GCFilterMin 0.45 -GCFilterMax 0.7 -sodiumConc 50.0 -magnesConc 1.5
```

## Set Up

Some commands depend on RDP ReadSeq and the open source program primer3. See RDPTools (https://github.com/rdpstaff/RDPTools) to install ReadSeq. 
