# CBT163
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. 
Due to amazing work by Alison Zhang and Jake Choi repos are no longer deleted.

```
//***FILE 163 IS FROM DAVID ANDREWS OF A. DUDA AND SONS, INC.       *   FILE 163
//*           IN OVIEDO, FLORIDA.  THIS PDS CONTAINS SOURCE FOR     *   FILE 163
//*           THE FOLLOWING:                                        *   FILE 163
//*                                                                 *   FILE 163
//*     email address:   dba@duda.com                               *   FILE 163
//*                                                                 *   FILE 163
//*           1.  ADJXAMI - LINKEDITS AS A FRONT-END TO MODULE      *   FILE 163
//*               HASPAMI IN HASPSSSM.  INSPECTS AND DISCARDS       *   FILE 163
//*               ALL CARD IMAGES WRITTEN TO AN INTERNAL READER     *   FILE 163
//*               DATASET THAT START WITH A BANG ("!") IN           *   FILE 163
//*               COLUMN 1.  YOU CAN INSERT COMMENTS IN JCL         *   FILE 163
//*               OR EVEN INSTREAM DATA.  AUTHOR: DAVID ANDREWS.    *   FILE 163
//*                                                                 *   FILE 163
//*           2.  ADJX006C - A JES2 EXIT #6.  PROVIDES A DEFAULT    *   FILE 163
//*               MODEL DSCB FOR NEW GENERATION DATASETS (REMOVING  *   FILE 163
//*               THE REQUIREMENT THAT EITHER A MODEL DSCB EXIST    *   FILE 163
//*               FOR EACH DEFINED GDG, OR THAT YOU SPECIFY ONE     *   FILE 163
//*               IN YOUR JCL).  DESIGNED TO WORK WITH IFG0EX0B     *   FILE 163
//*               (SEE BELOW).  AUTHOR: DAVID ANDREWS.              *   FILE 163
//*                                                                 *   FILE 163
//*           3.  ADMM02 - AN SMP USERMOD TO THE LINKAGE            *   FILE 163
//*               EDITOR.  REMOVES THE 3200-BYTE LIMITATION         *   FILE 163
//*               ON SYSLIN BLOCKSIZE.  THE OFFSETS ARE SET         *   FILE 163
//*               FOR THE DFP 2.4 LINKAGE EDITOR, BUT THIS          *   FILE 163
//*               PARTICULAR MOD HAS BEEN RUN ON OTHER              *   FILE 163
//*               VERSIONS (JUST CHANGE THE OFFSETS).               *   FILE 163
//*               AUTHOR: UNKNOWN.                                  *   FILE 163
//*                                                                 *   FILE 163
//*           4.  CATLG - CONTAINS "CATLG", "UNCATLG" AND           *   FILE 163
//*               "SCRATCH" TSO COMMANDS, WHICH ARE SIMILAR         *   FILE 163
//*               TO THEIR IEHPROGM COUNTERPARTS.  AUTHOR:          *   FILE 163
//*               DAVE PHILLIPS.                                    *   FILE 163
//*                                                                 *   FILE 163
//*           5.  CHARGEN - A BANNER PROGRAM THAT WAS FLOATING      *   FILE 163
//*               AROUND IN MY POSTGRADUATE DAYS, CIRCA 1975.       *   FILE 163
//*               AUTHOR: JAY ULLIUS.                               *   FILE 163
//*                                                                 *   FILE 163
//*           6.  DA - "DISPLAY ACTIVE" TSO CP.  LISTS ACTIVE       *   FILE 163
//*               ADDRESS SPACES AT YOUR TERMINAL, ALONG WITH       *   FILE 163
//*               THEIR CPU/EXCP/STORAGE UTILIZATION AND SWAP       *   FILE 163
//*               STATUS.  FULL-SCREEN 3270 ONLY (NO BATCH          *   FILE 163
//*               SUPPORT).  AUTHOR: DAVE PHILLIPS.                 *   FILE 163
//*                                                                 *   FILE 163
//*           7.  DD - LISTS CHARACTERISTICS OF CATALOGED AND       *   FILE 163
//*               UNCATALOGED DATASETS.  GOOD FOR GENERATION        *   FILE 163
//*               DATA GROUPS.  AUTHOR: DAVE PHILLIPS.              *   FILE 163
//*                                                                 *   FILE 163
//*           8.  WTO AND DOM - A PAIR OF LITTLE TSO COMMANDS.      *   FILE 163
//*               WTO WRITES NON-DELETABLE MESSAGES TO THE          *   FILE 163
//*               MVS CONSOLE, AND DOM DELETES THOSE MESSAGES.      *   FILE 163
//*               GREAT FOR WAKING UP THE OPERATOR (BEEP!)          *   FILE 163
//*               AUTHOR: DAVE PHILLIPS.                            *   FILE 163
//*                                                                 *   FILE 163
//*           9.  IFG0EX0B - INSTALLATION DCB OPEN EXIT.  PROVIDES  *   FILE 163
//*               DEFAULT BLOCKSIZES FOR PROGRAMS AND JCL THAT      *   FILE 163
//*               DON'T SUPPLY THEIR OWN.  FOR DASD, IT SELECTS     *   FILE 163
//*               A BLOCKSIZE CLOSE TO A HALF-TRACK.  FOR TAPE,     *   FILE 163
//*               IT SELECTS A BLOCKSIZE CLOSE TO 16K.  FOR DD      *   FILE 163
//*               DUMMY, VIO AND SUBSYSTEM DATASETS IT SELECTS A    *   FILE 163
//*               MINIMAL BLOCKSIZE.  NONE OF OUR INSTALLATION      *   FILE 163
//*               JCL SPECIFIES DCB=BLKSIZE=ANYTHING!  AUTHOR:      *   FILE 163
//*               DAVE PHILLIPS.                                    *   FILE 163
//*                                                                 *   FILE 163
//*           10. RSMAP - REAL STORAGE MAP.  PRODUCES A DETAILED    *   FILE 163
//*               SUMMARY OF REAL STORAGE USAGE FOR EACH ADDRESS    *   FILE 163
//*               SPACE.  TELLS YOU HOW MANY REAL STORAGE FRAMES    *   FILE 163
//*               ARE BEING USED FOR SUCH THINGS AS SQA, CSA,       *   FILE 163
//*               LPA, LSQA, PRIVATE AREA, NUCLEUS, FIXED FRAMES,   *   FILE 163
//*               VIO, ET CETERA.  YOU MAY HAVE TO INCREASE SOME    *   FILE 163
//*               TABLE SIZES IF YOU HAVE A LARGE NUMBER OF         *   FILE 163
//*               ADDRESS SPACES.  WORKS ONLY IN MVS/370.           *   FILE 163
//*               AUTHOR: DAVE PHILLIPS.                            *   FILE 163
//*                                                                 *   FILE 163
//*           11. S213RC30 - ELIMINATES THOSE S213-30 ABENDS THAT   *   FILE 163
//*               IBM SUPPLIED WITH DFP V2.  WHEN TWO PROGRAMS      *   FILE 163
//*               SIMULTANEOUSLY OPEN A PDS FOR OUTPUT, THE SECOND  *   FILE 163
//*               IS ABENDED S213-30.  WITH S213RC30 INSTALLED,     *   FILE 163
//*               THE SYSTEM ISSUES A WTOR TO THE OPERATOR AND      *   FILE 163
//*               WAITS FOR THE PDS RESOURCE TO BECOME AVAILABLE    *   FILE 163
//*               (THE OPERATOR CAN REPLY "CANCEL", IN WHICH CASE   *   FILE 163
//*               THE SECOND PROGRAM ABENDS S213-30 AS BEFORE).     *   FILE 163
//*               AUTHOR: DAVID ANDREWS.                            *   FILE 163
//*                                                                 *   FILE 163
//*          12.  ZAPDSCB - BATCH PROGRAM TO CHANGE THE ATTRIBUTES  *   FILE 163
//*               OF ANY DIRECT-ACCESS DATASET.  CAN BE USED TO     *   FILE 163
//*               MODIFY DCB CHARACTERISTICS, PROTECTION STATUS,    *   FILE 163
//*               EXPIRATION DATE, USE COUNT, AND SECONDARY SPACE   *   FILE 163
//*               AMOUNT.  AUTHOR: DAVE PHILLIPS.                   *   FILE 163
//*                                                                 *   FILE 163
```
