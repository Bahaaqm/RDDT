Bahaa Al-Musawi	<bahaa.almusawi@uokufa.edu.iq>
Faculty of Engineering,                                                                                                  
University of Kufa,                                                                                                          
AL Najaf, Iraq                                                                                                                                                                                                                                                

23th September, 2019

----------------------------------------------
OVERVIEW                                      
----------------------------------------------

This documentation explains the layout of the RDDT tool and gives an overview of
the necessary files to calculate RDDT parameters, test files, and the necessary
files to run RDDT tool. 

The directory structure is as follows: 

+ rqa
  - cal_parameter	<to estimate the parameters>
  - crp.m	<a Matlab script to plot recurrence plot>
  - false_nearest	<implement false nearest neighbour algorithm to find out embedding dimensions>
  - mutual	<implement mutual information algorithm to find out time delay>
  - normalize	<to normalise data>
  - parameter.pl	<to collect 200 seconds of BGP updates, necessary to calculate the parameters>
  - plot_alarms	<to plot detected BGP anomalies located in anomaly_timestamps> directory
  - pss.m	<a Matlab script to calculate the maximum phase space diameter. >
  - recurrence	<calculate RQA measurements>
  - rp	<RQA script>
  - test_email.pl	<to check email configuration and send a test email>
  + private	<contains others necessary functions required by pss.m and crp.m>
  
+ patch
  - patch.sh	<patch installation script to IPv6 support to Net::BGP module>
  - ipv6_bgpnet-0.1.patch	<IPv6 support patch to Net::BGP module>
- configuration.txt	<the configuration file of RTBADT tool>
- README-FIRST.txt	<this file>
- README-RTBADT.txt	<readme file for RDDT tool>
- realtime.sh	<bash script to enable real-time plot using Gnuplot>
- rtbadt-01.pl	<RTBADT tool>

----------------------------------------------
QUICK START GUIDE
----------------------------------------------

Before running RDDT tool, users need to run the following scripts:
1) <parameter.pl> script in the rqa directory, this script will collect
   200 seconds of BGP updates then exit. The output of this script is
   plot.txt in the rqa directory. This is necessary to calculate RQA
   parameters() time delay and embedding dimensions).
   
2) <cal_parameter> script in the rqa directory, this script will estimate
   the values of time delay and embedding dimensions. Although this script
   has been tested, there is no guarantee that the estimation is correct.
   It is recommended that send the file plot.txt in the rqa directory to the
   author <bahaa.almusawi@uokufa.edu.iq> to calculate the proper parameters.
   
3) <test_email.pl> this is only necessary if the users need to enable e-mail
   notification. However, before running this script, you need to edit the
   configuration file <configuration.txt>.

4) If you want to enable e-mail notification, you need to allow access
   to less secure apps.  For example, allowing less secure apps in gmail 
   account can be activated through the following link 
   https://myaccount.google.com/lesssecureapps.
   
----------------------------------------------