Real-Time Inter-domain routing Disruption Detection Tool (RDDT) is a tool for UNIX
operating systems. To detect Inter-domain  routing disruptions as AS-level,
RDDT is peered with the intended AS to detect disruptions.

RDDT tool save inter-domain routing features and the detected disruptions in plot.txt
file located in <anomaly_timestamp> directory. RDADT needs many parameters
which can be changed in configuration.txt file. BGP session and message
handling are done by Net::BGP v0.16,a Perl module that implementsBGP-4
inter-domain routing protocol.
This tool helps ISPs operators to detect BGP anomalies at an early stage.
