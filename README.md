# PrimerDesign

The Primer Design terminal program produces thermodynamically stable primer pairs for qPCR from an input of aligned nucleotide sequences. This is the main subcommand known as select. A preliminary subcommand is screen which produces a graph of the coverage and the entropy for each position of the input reference sequences. The input nucleotide sequences should be in the FASTA format. 

## Set Up

Some commands depend on RDP ReadSeq and the open source program primer3 that can be found online. See RDPTools (https://github.com/rdpstaff/RDPTools) to install ReadSeq. 

## Usage

The default subcommand to Primer Design is select. 


java -Xmx8g -jar /path/to/PrimerDesign.jar [--help] (-i|--input) <FastaFile>
            (-o|--onput) <Output>
    --assayMax <assayMax>                               assayMax (default:
                                                        20) - Maxiumum
                                                        number of assays
                                                        allowed - one
                                                        degenerate primer
                                                        pair per assay
    --degenMax <degenMax>                               degenMax (default:
                                                        8) - Maximum
                                                        degeneracy per
                                                        primer pair.
                                                        Nondegenerate
                                                        primers = 1.
                                                        Recommend no
                                                        higher than 10
    --forwardMaxPos <forwardMaxPos>                     forwardMaxPos
                                                        (default: 120) -
                                                        Foward oligo
                                                        maximum position
                                                        to end
                                                        enumeration.
                                                        Needed if
                                                        SlidingScale is
                                                        false
    --forwardMinPos <forwardMinPos>                     forwardMinPos
                                                        (default: 100) -
                                                        Foward oligo
                                                        minimum position
                                                        to begin
                                                        enumeration.
                                                        Needed if
                                                        SlidingScale is
                                                        false
    --GCFilterMax <GCFilterMax>                         GCFilterMax
                                                        (default: 0.70) -
                                                        G+C content filter
                                                        maximum percent.
                                                        Recommend leaving
                                                        at default if
                                                        unsure
    --GCFilterMin <GCFilterMin>                         GCFilterMin
                                                        (default: 0.45) -
                                                        G+C content filter
                                                        minimum percent.
                                                        Recommend leaving
                                                        at default if
                                                        unsure
 -h,--help                                              Shows this help
    --hairMax <hairMax>                                 hairMax (default:
                                                        35) - Hairpin
                                                        maximum
                                                        temperature
    --homoMax <homoMax>                                 homoMax (default:
                                                        35) - Homodimer
                                                        maximum
                                                        temperature
 -i,--input <input>                                     Input .fasta or
                                                        .fa file. Contains
                                                        aligned gene
                                                        sequences
    --isHenikoffWeightNeeded <isHenikoffWeightNeeded>
                                                        isHenikoffWeightNe
                                                        eded (default:
                                                        false) - Henikoff
                                                        Weighting Method.
                                                        Set to 'true' or
                                                        't' if you would
                                                        like this
                                                        weighting method
                                                        results aswell as
                                                        uniform results.
                                                        Will give the
                                                        highest weight to
                                                        unique sequences
                                                        based on bases at
                                                        each position.
    --isTreeWeightNeeded <isTreeWeightNeeded>           isTreeWeightNeeded
                                                        (default: false)-
                                                        A phylogenetic
                                                        tree weighting
                                                        method.  Must
                                                        include .tree
                                                        file. Set to
                                                        'true' or 't' if
                                                        you would like
                                                        this weighting
                                                        method results
                                                        aswell as uniform
                                                        results. Will give
                                                        the highest weight
                                                        to sequences
                                                        closest to the
                                                        root
    --magnesConc <magnesConc>                           magnesConc
                                                        (default: 1.5) -
                                                        Divalent magnesium
                                                        concentration for
                                                        thermodynamic
                                                        calculations
    --maxMismatches <maxMismatches>                     maxMismatches
                                                        (default: 2) -
                                                        Oligo mismatch
                                                        maximum. Recommend
                                                        setting between 0
                                                        and 3
    --NoPoly3GCFilter <NoPoly3GCFilter>                 NoPoly3GCFilter
                                                        (default: true) -
                                                        If true, filter to
                                                        remove any oligo
                                                        generated with
                                                        three Guanines or
                                                        three Cytosines in
                                                        a row
    --NoTEndFilter <NoTEndFilter>                       NoTEndFilter
                                                        (default: true) -
                                                        If true, filter to
                                                        remove any oligo
                                                        generated with a
                                                        Thymine base at
                                                        end
 -o,--GraphOutput <GraphOutput>                         If screen
                                                        subcommand is ran,
                                                        then this is the
                                                        output directory
                                                        for graph results
    --oligoMaxSize <oligoMaxSize>                       oligoMaxSize
                                                        (default: 30) -
                                                        Maximum oligo
                                                        size; Recommend no
                                                        longer than 30 bp
    --oligoMinSize <oligoMinSize>                       oligoMinSize
                                                        (default: 22) -
                                                        Minimum oligo
                                                        size; Recommend no
                                                        shoter than 15 bp
    --os <os>                                           Operating System :
                                                        linux/mac
                                                        (default: mac)
    --output <output>                                   Full path to
                                                        output file (for
                                                        select)
    --PolyRunFilter <PolyRunFilter>                     PolyRunFilter
                                                        (default: 4) -
                                                        Poly Run max
                                                        filter
    --productLengthMax <productLengthMax>               productLengthMax
                                                        (default: 200) -
                                                        Maximum amplicon
                                                        product length.
                                                        Needed if
                                                        SlidingScale is
                                                        true
    --productLengthMin <productLengthMin>               productLengthMin
                                                        (default: 100) -
                                                        Minimum amplicon
                                                        product length.
                                                        Needed if
                                                        SlidingScale is
                                                        true
    --reverseMaxPos <reverseMaxPos>                     reverseMaxPos
                                                        (default: 370) -
                                                        Reverse oligo
                                                        maximum position
                                                        to end
                                                        enumeration.
                                                        Needed if
                                                        SlidingScale is
                                                        false
    --reverseMinPos <reverseMinPos>                     reverseMinPos
                                                        (default: 350) -
                                                        Reverse oligo
                                                        minimum position
                                                        to begin
                                                        enumeration.
                                                        Needed if
                                                        SlidingScale is
                                                        false
    --SlidingScale <SlidingScale>                       SlidingScale
                                                        (default: true) -
                                                        If true, then
                                                        forward and
                                                        reverse primer
                                                        pairs are built
                                                        with a sliding
                                                        window between the
                                                        given amplicon
                                                        product minimum
                                                        and maximum
                                                        length. If false,
                                                        the pairs will be
                                                        built between the
                                                        forward and
                                                        reverse given min
                                                        and max.
    --sodiumConc <sodiumConc>                           sodiumConc
                                                        (default: 50) -
                                                        Monovalent sodium
                                                        concentration for
                                                        thermodynamic
                                                        calculations
    --subcommand <subcommand>                           select subcommand:
                                                        select - file
                                                        output of
                                                        individual
                                                        degenerate primer
                                                        pairs with
                                                        sequences
                                                        theoretically hit
                                                        / screen - graph
                                                        output of the
                                                        proportional
                                                        theoretical
                                                        uniform coverage
                                                        at each position
                                                        (default: select)
 -t,--treeinput <treeinput>                             File (.tree)
                                                        containing
                                                        phylogentic
                                                        relationship of
                                                        the input
                                                        sequences. In
                                                        Newick format.
                                                        Must have if tag
                                                        -isTreeWeightNeede
                                                        d is true
    --tempMax <tempMax>                                 tempMax (default:
                                                        63) - Oligo max
                                                        melting
                                                        temperature
    --tempMin <tempMin>                                 tempMin (default:
                                                        55) - Oligo min
                                                        melting
                                                        temperature
                                                        
                                                        

RDP Primer Design Subcommands: Screen and Select

Screen – command used to generate a graphical representation of the coverage and entropy at each position of the reference set. A proportional bar graph of the theoretical uniform coverage is calculated at any given position as the summation of all possible targets hit divided by the total number of sequences. 

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



