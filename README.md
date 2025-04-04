# CBT223
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. GitHub repos will be deleted and created during this period...

```
//***FILE 223 IS THE FREE TAPE MANAGEMENT SYSTEM (FTMS) WHICH       *   FILE 223
//*           WAS SUBMITTED SEMI-ANONYMOUSLY.  THIS SYSTEM KEEPS    *   FILE 223
//*           COMPLETE TRACK OF ALL SL TAPES THAT WERE MOUNTED      *   FILE 223
//*           ON YOUR SYSTEM, AND IT HAS AN EXTENSIVE SET OF        *   FILE 223
//*           REPORTS.  FILE 224 CONTAINS SAMPLE OUTPUT FROM        *   FILE 223
//*           THIS SYSTEM.                                          *   FILE 223
//*                                                                 *   FILE 223
//*   -  -  -  -  -  -  -  -  -  -  -  -  -  -  -  -  -  -  -  -    *   FILE 223
//*                                                                 *   FILE 223
//*                FREE TAPE MANAGEMENT SYSTEM                      *   FILE 223
//*                                                                 *   FILE 223
//*      This is the Free Tape Management System (FTMS,             *   FILE 223
//*      pseudonym ITMS) which has been submitted                   *   FILE 223
//*      semi-anonymously.  Please direct inquiries to Sam          *   FILE 223
//*      Golob sbgolob@cbttape.org .                                *   FILE 223
//*                                                                 *   FILE 223
//*      I AM NOT THE AUTHOR OF THIS SYSTEM, BUT I WILL BE GLAD     *   FILE 223
//*      TO DIRECT YOU TO HIM FOR ADVICE AND/OR SUPPORT.            *   FILE 223
//*                                                                 *   FILE 223
//*      THIS IS A COMPLETE TAPE MANAGEMENT SYSTEM WHICH            *   FILE 223
//*      CAN KEEP TRACK OF A TAPE LIBRARY OF ANY SIZE.  AS          *   FILE 223
//*      WRITTEN, IT WILL NOT KICK DOWN A WRONG TAPE, BUT IT        *   FILE 223
//*      WILL TELL YOU EVERYTHING THAT HAS HAPPENED IN YOUR         *   FILE 223
//*      TAPE LIBRARY.  ALL TAPE ACTIVITY IS LOGGED.                *   FILE 223
//*                                                                 *   FILE 223
//*      THIS SYSTEM KEEPS FULL TRACK OF ALL THE TAPES IN           *   FILE 223
//*      YOUR LIBRARY, AND YOU HAVE A SIZABLE COLLECTION OF         *   FILE 223
//*      REPORTS TO TELL YOU WHAT TAPES ARE SOON TO REACH           *   FILE 223
//*      "SCRATCH STATUS", ETC.  SEE MEMBER ITMSFUNC TO LOOK        *   FILE 223
//*      AT THE NUMBER OF REPORTS AND OTHER FUNCTIONS WHICH         *   FILE 223
//*      ARE AVAILABLE WITH THIS SYSTEM.                            *   FILE 223
//*                                                                 *   FILE 223
//*      MEMBERS OF THIS PDS ARE AS FOLLOWS:                        *   FILE 223
//*                                                                 *   FILE 223
//*      ITMS000A  -  THIS IS ASSEMBLER SOURCE FOR THE MAIN         *   FILE 223
//*                   PROGRAM WHICH RUNS ITMS.                      *   FILE 223
//*                                                                 *   FILE 223
//*      ITMPAR01  -  THIS IS ASSEMBLER SOURCE FOR THE ITMS         *   FILE 223
//*                   PARSER.                                       *   FILE 223
//*                                                                 *   FILE 223
//*      ITMDBDEF  -  THIS IS JCL TO DEFINE THE CONTROL             *   FILE 223
//*                   DATASETS THAT ARE NEEDED TO RUN ITMS.         *   FILE 223
//*                                                                 *   FILE 223
//*      ITMSFUNC  -  THIS MEMBER SUPPLIES SAMPLE EXECUTION         *   FILE 223
//*                   PARMS TO EXECUTE THE VARIOUS FUNCTIONS        *   FILE 223
//*                   WHICH ITMS IS CAPABLE OF PROVIDING.           *   FILE 223
//*                                                                 *   FILE 223
//*      ITMS705I  -  THIS IS AN AOC CLIST TO DRIVE THE ITMS        *   FILE 223
//*                   SYSTEM.  IT GETS KICKED OFF BY THE            *   FILE 223
//*                   IEC705I TAPE MESSAGE, THROUGH THE             *   FILE 223
//*                   ITMS705M MESSAGE TABLE ENTRY IN AOC.  IF      *   FILE 223
//*                   YOU HAVE A DIFFERENT AUTOMATED OPERATIONS     *   FILE 223
//*                   PACKAGE THAN IBM'S AOC, THIS MEMBER CAN       *   FILE 223
//*                   BE ADAPTED TO THE OTHER SYSTEM.               *   FILE 223
//*                                                                 *   FILE 223
//*      ITMS705M  -  THIS IS AN AOC/NETVIEW MESSAGE TABLE          *   FILE 223
//*                   ENTRY TO DRIVE THE ITMS CLIST FROM THE        *   FILE 223
//*                   IEC705I CONSOLE MESSAGE.  IF YOU HAVE A       *   FILE 223
//*                   DIFFERENT AUTOMATED OPERATIONS PACKAGE        *   FILE 223
//*                   THAN IBM'S AOC, THIS MEMBER CAN BE            *   FILE 223
//*                   ADAPTED TO THE OTHER SYSTEM.                  *   FILE 223
//*                                                                 *   FILE 223
//*      ITMSRUN   -  THE STARTED PROC THAT RUNS ITMS.  KICKED      *   FILE 223
//*                   OFF BY THE CLIST.                             *   FILE 223
//*                                                                 *   FILE 223
//*      ITMSJOB   -  (ON FILE 224).  SAMPLE PRINTOUT OF AN         *   FILE 223
//*                   ITMS RUN.                                     *   FILE 223
//*                                                                 *   FILE 223
//*      ITMSPRT   -  (ON FILE 224).  SAMPLE PRINTOUT OF AN         *   FILE 223
//*                   ITMS RUN WITH MANY OPTIONS.                   *   FILE 223
//*                                                                 *   FILE 223
//*      THE SEQUENCE OF EVENTS IN EXECUTING THIS SYSTEM            *   FILE 223
//*      IS AS FOLLOWS:  (IF YOUR AUTOMATION PACKAGE IS             *   FILE 223
//*      NOT IBM'S AOC, YOU MUST CUSTOMIZE ITMS705M AND             *   FILE 223
//*      ITMS705I TO YOUR AUTOMATION PACKAGE.)                      *   FILE 223
//*                                                                 *   FILE 223
//*         1.  THE TAPE JOB PRODUCES AN IEC705I MOUNT              *   FILE 223
//*             MESSAGE.                                            *   FILE 223
//*                                                                 *   FILE 223
//*         2.  THE NETVIEW MESSAGE TABLE ENTRY INTERCEPTS          *   FILE 223
//*             THE IEC705I MESSAGE AND KICKS OFF THE AOC           *   FILE 223
//*             ITMS705I CLIST, WHICH STARTS THE ITMS PROC          *   FILE 223
//*             USING APPROPRIATE PARAMETERS THAT WERE              *   FILE 223
//*             PARSED FROM THE IEC705I MESSAGE.                    *   FILE 223
//*                                                                 *   FILE 223
//*         3.  THE ITMS STARTED TASK UPDATES THE ITMS              *   FILE 223
//*             DATABASE.  SEE THE SAMPLE REPORT FROM FILE          *   FILE 223
//*             224.                                                *   FILE 223
//*                                                                 *   FILE 223
//*         4.  YOU RUN "ANY OF MANY" EXECUTIONS OF ITMS            *   FILE 223
//*             WITH APPROPRIATE PARAMETERS (SEE MEMBER             *   FILE 223
//*             ITMSFUNC) TO PRODUCE ALL THE REPORTS YOU            *   FILE 223
//*             NEED AND WANT.  THERE ARE MANY DIFFERENT            *   FILE 223
//*             REPORTS THAT CAN BE PRODUCED.                       *   FILE 223
//*                                                                 *   FILE 223
```
