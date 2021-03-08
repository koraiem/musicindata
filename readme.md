This project intends to inegst mxl files into data sets that are readable by common database/data analytics software

As a proof-of-concept I'm using libfmp (created by audiolabs) to read musicXML files and export them to CSV files.
These CLV files can then be ingested into any DBMS (ex: MySQL) or a data analytics tool (ex: Tableau)

An example tableau workbook included parses a CSV file of Pachelbel Canon in D, a few extra tweaks to the data allow creating the following labels:
* Use the midi pitch value to label each note
* Split the unique note IDs into Octaves
* Assigning a tempo value allows converting note start times/end times into actual timestamps in ss:ms format (need to manually check the tempo on the original score, or guess it by checking the duration of the piece if a midi/audio file is available)
* Label notes at the start of a new measure and a new hypermeasure (need to manually check the time signature on the original score)
* Velocity is an arbitrary value in basic midi files, but in multi-instrument complex files it could reflect true volume of the instrument

TODO:
* Visualize musical scores from data files
* Build a dataset of musical scales, and match it with different pieces
* Automatically guess the tempo of the piece
* Automatically guess the time signature of the piece
* Generate similar data files from real audio files