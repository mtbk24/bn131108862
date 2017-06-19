bn131108862 GBMwLAT


grbm and sbpl:  both were good fits to the data, good errors, good stats.

copl:  not a good fit to the high energy data.

grbm+lpow:  good 1 sigma errors.  Good fit to data and params.  Worse than grbm alone.  Flags only on PL params at 2-sigma.
   1    1   grbm       alpha               -0.619964    +/-  0.100977     
   2    1   grbm       beta                -2.23348     +/-  5.05686E-02  
   3    1   grbm       tem        keV      214.244      +/-  28.0236      
   4    1   grbm       norm                3.65281E-02  +/-  2.17067E-03  
   5    2   lpow       plIndex    NONE     -1.89708     +/-  8.77014E-02  
   6    2   lpow       norm                1.79432E-03  +/-  6.18277E-04


sbpl+lpow:  good fit to the data and params.  Good 1 sigma errors.  Only Flags on PL params at 2-sigma.  nan on PL lower errors.
   1    1   sbpl       alpha      NONE     -0.858886    +/-  9.47912E-02  
   2    1   sbpl       beta       NONE     -2.23897     +/-  4.42872E-02  
   3    1   sbpl       ebreak     keV      180.357      +/-  15.0106      
   4    1   sbpl       norm                2.35709E-02  +/-  6.84508E-04  
   5    2   lpow       plIndex    NONE     -1.87063     +/-  9.47585E-02  
   6    2   lpow       norm                1.35334E-03  +/-  6.96756E-04

copl+lpow:  okay fit.  PL would be better if it leveled out at -2, but the lower energy data due to the COPL won't allow it to do so.  SO it cuts upward through the LAT/LLE data.  Seen this in a few other bursts with good LAT data.  Good errors.
   1    1   copl       cplIndex   NONE     -0.569612    +/-  8.35658E-02  
   2    1   copl       highEcut   NONE     228.350      +/-  21.9130      
   3    1   copl       norm                3.30072E-02  +/-  1.27017E-03  
   4    2   lpow       plIndex    NONE     -1.78339     +/-  2.08530E-02  
   5    2   lpow       norm                3.16155E-03  +/-  4.43156E-04


grbm+blackb:  2 options.  good fit, good errors, no flags.  Neither one of the bbody's really stick through in the combination model.  This might mean neither are significant enough to be better than the grbm alone.  Compare the ratio of the norm's to others where the bbody sticks out on the plots.  i.e. overshoots the grbm model.  BIC favors the grbm alone model but the AIC favors these two grbm+blackb models. This is a sign that BIC captures significance levels better than AIC.
   1    1   grbm       alpha               -1.00062     +/-  6.46468E-02  
   2    1   grbm       beta                -2.18505     +/-  1.60754E-02  
   3    1   grbm       tem        keV      396.027      +/-  80.5715      
   4    1   grbm       norm                2.73475E-02  +/-  2.96973E-03  
   5    2   blackb     kT         keV      43.1393      +/-  5.03784      
   6    2   blackb     norm                4.04303E-06  +/-  2.34698E-06
    or:  this one only has flags on the norm params and only at 2 sigma.
   1    1   grbm       alpha               -0.775247    +/-  6.22595E-02  
   2    1   grbm       beta                -2.21833     +/-  1.60027E-02  
   3    1   grbm       tem        keV      255.389      +/-  26.6999      
   4    1   grbm       norm                3.64034E-02  +/-  1.77780E-03  
   5    2   blackb     kT         keV      5.58068      +/-  1.11109      
   6    2   blackb     norm                1.38635E-03  +/-  5.58606E-04 

sbpl+blackb:  started out with a set of parameters (first one listed) and during the error run, I got a new list of parameters (second listed).  The second one had good errors and only threw flags at 2-sigma level for the BBODY params.  This is the first time I've seen a BBODY jump to kT = 77.  Most stay around 40 keV.  We used the 2nd on in BXA.
I then tried the 3rd option on this list, with a kT = 6 and the 1-sigma errors were fine.  No flags, no change in parameters.  When it went for the 2-sigma errors, it changed the fit to the 2nd option down, with kT = 77.  This is interesting becuase I then went back and re-ran grbm+blackb to try and get kT to stay stable around kT = 77 (or any value near it) and I could not get it to stay.  kT kept going to the kT = 43, which we found for grbm+blackb.  *** Check to make sure the BB isn't artificially inflating the sbpl at its center.
This changed to the 2nd one listed.
   1    1   sbpl       alpha      NONE     -1.06887     +/-  6.65499E-02  
   2    1   sbpl       beta       NONE     -2.19449     +/-  1.60771E-02  
   3    1   sbpl       ebreak     keV      216.271      +/-  38.7092      
   4    1   sbpl       norm                2.24184E-02  +/-  1.89733E-03  
   5    2   blackb     kT         keV      40.5601      +/-  9.58310      
   6    2   blackb     norm                3.22714E-06  +/-  4.14271E-06
     This is the one we saved as (1).
   1    1   sbpl       alpha      NONE     -1.00759     +/-  3.23252E-02  
   2    1   sbpl       beta       NONE     -2.15183     +/-  2.81695E-02  
   3    1   sbpl       ebreak     keV      152.503      +/-  25.3142      
   4    1   sbpl       norm                2.32112E-02  +/-  8.35418E-04  
   5    2   blackb     kT         keV      77.8334      +/-  8.63250      
   6    2   blackb     norm                6.42563E-07  +/-  3.67409E-07
     or a 3rd option with a low kT, we call this (2):
	 for this one, I only saved the 1-sigma errors because they were really good and normally I wouldn't have done 2-sigma.  But 2-sigma would have changed this fit to kT = 77 option.  SO this is worth keeping, noting and runninb BXA on.
   1    1   sbpl       alpha      NONE     -0.943055    +/-  5.05756E-02  
   2    1   sbpl       beta       NONE     -2.21013     +/-  1.32751E-02  
   3    1   sbpl       ebreak     keV      184.904      +/-  11.1561      
   4    1   sbpl       norm                2.48300E-02  +/-  3.45287E-04  
   5    2   blackb     kT         keV      5.98205      +/-  1.71180      
   6    2   blackb     norm                7.89688E-04  +/-  4.95397E-04  


copl+blackb:  nothing works here becuase there is no PL component to account for the high-energy LAT/LLE data.  This was the best I could get.  Not a good fit!  No errors.  No reason for them.
   1    1   copl       cplIndex   NONE     -0.823566    +/-  4.70927E-02  
   2    1   copl       highEcut   NONE     305.678      +/-  25.1084      
   3    1   copl       norm                3.39815E-02  +/-  1.18762E-03  
   4    2   blackb     kT         keV      3.60114      +/-  0.471594     
   5    2   blackb     norm                7.57362E-03  +/-  5.70981E-04

grbm+blackb+lpow:  Good fit, good errors, only flags at 1-sigma level on PL.  BB isn't very significant.  Doens't contribute to the overall model.  Probably not a good fit for this reason.
   1    1   grbm       alpha               -0.546810    +/-  0.159706     
   2    1   grbm       beta                -2.23544     +/-  5.00741E-02  
   3    1   grbm       tem        keV      195.753      +/-  35.8735      
   4    1   grbm       norm                3.85089E-02  +/-  3.34244E-03  
   5    2   blackb     kT         keV      6.58856      +/-  1.90523      
   6    2   blackb     norm                6.96425E-04  +/-  3.91991E-04  
   7    3   lpow       plIndex    NONE     -1.90479     +/-  0.100987     
   8    3   lpow       norm                1.62046E-03  +/-  6.30848E-04

sbpl+blackb+lpow:  This one I had problems with.  I couldn't get it to stick at similar params to grbm+blackb+lpow.  1-sigma errors had issues with the PL only.
   1    1   sbpl       alpha      NONE     -0.861370    +/-  0.148765     
   2    1   sbpl       beta       NONE     -2.16137     +/-  8.75408E-02  
   3    1   sbpl       ebreak     keV      139.777      +/-  30.3379      
   4    1   sbpl       norm                2.26405E-02  +/-  1.35982E-03  
   5    2   blackb     kT         keV      83.2353      +/-  11.1548      
   6    2   blackb     norm                4.99964E-07  +/-  4.06790E-07  
   7    3   lpow       plIndex    NONE     -1.96409     +/-  0.464776     
   8    3   lpow       norm                1.02535E-03  +/-  1.54538E-03


copl+blackb+lpow:  good fit, good errors with no flags.
   1    1   copl       cplIndex   NONE     -0.592705    +/-  0.151216     
   2    1   copl       highEcut   NONE     274.029      +/-  46.6669      
   3    1   copl       norm                2.52679E-02  +/-  2.62700E-03  
   4    2   blackb     kT         keV      29.2123      +/-  4.47713      
   5    2   blackb     norm                1.29642E-05  +/-  7.57257E-06  
   6    3   lpow       plIndex    NONE     -1.80266     +/-  2.46774E-02  
   7    3   lpow       norm                3.63279E-03  +/-  6.08360E-04  






