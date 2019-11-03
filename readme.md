
# Compiling and Running
You need a C++ compiler. GNU g++ is probably the best choice. Check that it is installed (by typing g++ at the prompt). If it is not installed yet, install it!

## Copy the executable file (wordcount) to the bin directory in HDFS:
  hadoop dfs -mkdir bin                    (Note: it should already exist!)
  hadoop dfs -put  wordcount   bin/wordcount

## Run the program!
  hadoop pipes -D hadoop.pipes.java.recordreader=true  \ 
                   -D hadoop.pipes.java.recordwriter=true \
                   -input dft1  -output dft1-out  \
                   -program bin/wordcount

## Output
 hadoop dfs -text dft1-out/part-00000
 
  "Come   1
  "Defects,"      1
  "I      1
  "Information    1
  "J"     1
  "Plain  2
  ...
  zodiacal        2
  zoe)_   1
  zones:  1
  zoo.    1
  zoological      1
  zouave's        1
  zrads,  2
  zrads.  1