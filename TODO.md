# Things to do

1. Copy data off Dropbox to a stable location we can easily mount or scp from, make a note of that in the Readme
2. Initial pipeline:
    - Pre-processing: The data is generally in folders with wavs and textgrids that may be hard to match one to another, and which differ from sub-corpus to sub-corpus; should probably, for each sub-corpus, set up scripts to copy the raw data into some standardized organization, so that the pipeline can run smoothly
    - Feature extraction:
        - input - wav and annotation file
        - output - various types of vector features - start with, for example, fixed time window MFCCs - want to be able to move on to try out different features (e.g. RNN) easily
        - First reproduce the feature extraction from the supervised monkey tools (fixed dimension MFCCs after noise reduction and noise subtraction)
            - http://bit.ly/2v2xWo7 - line 221 and functions called there - _extract_noise, extract_features_at - which also relies on noise reduction code in Maarten's spectral package
            - See also the paper (http://asa.scitation.org/doi/full/10.1121/1.4954887)
        - Then make sure that we have tools to easily write other feature extraction scripts or modules with the same input and output
    - ABX - start by doing tests for the following comparisons:
      - Campbell: K+ vs W+
      - Campbell: K+ vs H
      - Campbell: K vs H
      - Blue Fuller: H vs P
      - Blue Fuller: H+ vs P
      - Blue Fuller: A vs H
      - Blue Fuller: A vs H+
      - Blue Fuller: A* vs H
      - Blue Fuller: A* vs H+
      - Blue Murphy: P vs H
      - Putty: P vs H
      - Titi: A vs B
      - Colobus: R vs S
3. Comparison of two different sets of labels for Blue monkeys
    - James Fuller and Derek Murphy propose two different classification schemes for the calls of Blue monkeys. Once we have a good set of features, a good first step for using them would be to try and evaluate which of these two classification schemes is "better" in some well defined sense.
