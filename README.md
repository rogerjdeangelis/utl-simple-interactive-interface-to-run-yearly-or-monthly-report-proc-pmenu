# utl-simple-interactive-interface-to-run-yearly-or-monthly-report-proc-pmenu
Simple interactive interface to run yearly or monthly report proc pmenu 
    %let pgm=utl-simple-interactive-interface-to-run-yearly-or-monthly-report-proc-pmenu;

    Simple interactive interface to run yearly or monthly report proc pmenu

    github
    http://tinyurl.com/44nycw35
    https://github.com/rogerjdeangelis/utl-simple-interactive-interface-to-run-yearly-or-monthly-report-proc-pmenu

    You may need the classic editor for this


    RELATED REPOS

    https://github.com/rogerjdeangelis/utl-interactive-processing-using-classic-SAS-prompt-user-for-input
    https://github.com/rogerjdeangelis/utl-intergrating-interactive-python-popup-checkboxes-with-sas-using-pyqt4-and-tkinter
    https://github.com/rogerjdeangelis/utl_interactive_checkbox_input_using_python_tkinter_to_subset_sas_dataset
    https://github.com/rogerjdeangelis/utl_interactive_input_to_load_a_specified_web_table_into_wps_sas
    https://github.com/rogerjdeangelis/utl_interactive_menu_driven_job_submission_pmenu
    https://github.com/rogerjdeangelis/utl_interactive_text_box_to_set_type_and_length_for_text_file_input
    https://github.com/rogerjdeangelis/utl_sas_python_interactive_checkbox_input_to_sas
    https://github.com/rogerjdeangelis/utl-python-very-simple-interactive-sqllite-dashboard-to-query-roger-deangelis-repositories

    /*               _     _
     _ __  _ __ ___ | |__ | | ___ _ __ ___
    | `_ \| `__/ _ \| `_ \| |/ _ \ `_ ` _ \
    | |_) | | | (_) | |_) | |  __/ | | | | |
    | .__/|_|  \___/|_.__/|_|\___|_| |_| |_|
    |_|
    */

    /************************************************************************************************************************/
    /*                                   |                                                |                                 */
    /*    INPUT TWO PROGRAM FILES        |               PROCESS                          | OUTPUT LOG AND LIST             */
    /*                                   |                                                |                                 */
    /*                                   |                                                |                                 */
    /* Two programs Male & Female        | This is a pull down menu.                      | C:/UTL/MALES.LOG                */
    /*                                   | You have to click on 'Gender' in the taskbar,  | ================                */
    /* c:/utl/monthly.sas                | then a pull down will appear with options      | NOTE: PROCEDURE PRINTTO used    */
    /* ==================                | Males/Fenales click on Males to get the output |       (Total process time):     */
    /* proc print data=                  |                                                |       real time 0.00 seconds    */
    /*   sashelp.class(where=(sex='M')); | +--------------------------------------------+ | 2  proc print data=             */
    /* Title "Males"         ;           | | [ File GENDER Windows ]                    | | 3  sashelp.class                */
    /* run;                              | |--------------------------------------------| |        (where=(sex='M'));       */
    /*                                   | |                                            | | 4  Title "Males";               */
    /* c:/utl/monthly.sas                | |               Gender                       | | NOTE: There are 10 observations */
    /* ==================                | |                      _                     | |    read from the data set       */
    /* proc print data=                  | |             Males   [X]                    | |    SASHELP.CLASS WHERE sex='M'; */
    /*  sashelp.class(where=(sex='M'));  | |                      _                     | | NOTE: PROCEDURE PRINT used      */
    /* Title "Females" ;                 | |             Females [_]                    | |       (Total process time):     */
    /* run;                              | |                                            | |       real time 0.01 seconds    */
    /*                                   | +--------------------------------------------+ | 5  proc printto;                */
    /*                                   |                                                | 6  run;                         */
    /*                                   |                                                | NOTE: PROCEDURE PRINTTO used    */
    /*                                   |                                                |      (Total process time):      */
    /*                                   |                                                |       real time 0.00 seconds    */
    /*                                   |                                                |                                 */
    /*                                   |                                                | C:/UTL/MALES.LST                */
    /*                                   |                                                | ================                */
    /*                                   |                                                |  Males                          */
    /*                                   |                                                |                                 */
    /*                                   |                                                |  Name    Sex  Age Height Weight */
    /*                                   |                                                |                                 */
    /*                                   |                                                |  Alfred   M    14  69.0   112.5 */
    /*                                   |                                                |  Henry    M    14  63.5   102.5 */
    /*                                   |                                                |  James    M    12  57.3    83.0 */
    /*                                   |                                                |  Jeffrey  M    13  62.5    84.0 */
    /*                                   |                                                |  John     M    12  59.0    99.5 */
    /*                                   |                                                |  Philip   M    16  72.0   150.0 */
    /*                                   |                                                |  Robert   M    12  64.8   128.0 */
    /*                                   |                                                |  Ronald   M    15  67.0   133.0 */
    /*                                   |                                                |  Thomas   M    11  57.5    85.0 */
    /*                                   |                                                |  William  M    15  66.5   112.0 */
    /*                                   |                                                |                                 */
    /************************************************************************************************************************/

    /*                   _
    (_)_ __  _ __  _   _| |_
    | | `_ \| `_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    */

    * SAVE PROGRAMS, LOG AND LIST IN C:\UTL DIRECTORY;

    filename ft15f001 "c:\utl\males.sas";
    parmcards4;
    proc printto print="c:\utl\males.lst"
                 log="c:\utl\males.log" ;
    run;
    proc print data=
         sashelp.class(where=(sex='M'));
    Title "Males";
    proc printto;
    run;
    ;;;;
    run;quit;


    filename ft15f001 "c:\utl\females.sas";
    parmcards4;
    proc printto print="c:\utl\females.lst"
                 log="c:\utl\females.log" ;
    run;
    proc print data=
         sashelp.class(where=(sex='F'));
    Title "Females";
    run;
    proc printto;
    run;
    ;;;;
    run;quit;

    /**************************************************************************************************************************/
    /*                                          |                                                                             */
    /* c:\utl\males.sas                         |     c:\utl\females.sas                                                      */
    /* ================                         |     ================                                                        */
    /* proc printto print="c:\utl\males.lst"    |     proc printto print="c:\utl\females.lst"                                 */
    /*              log="c:\utl\males.log" ;    |                  log="c:\utl\females.log" ;                                 */
    /* run;                                     |     run;                                                                    */
    /* proc print data=                         |     proc print data=                                                        */
    /*      sashelp.class(where=(sex='M'));     |          sashelp.class(where=(sex='F'));                                    */
    /* Title "Males";                           |     Title "Females";                                                        */
    /* proc printto;                            |     proc printto;                                                           */
    /* run;                                     |     run;                                                                    */
    /*                                          |                                                                             */
    /**************************************************************************************************************************/

    /*
     _ __  _ __ ___   ___ ___  ___ ___
    | `_ \| `__/ _ \ / __/ _ \/ __/ __|
    | |_) | | | (_) | (_|  __/\__ \__ \
    | .__/|_|  \___/ \___\___||___/___/
    |_|
    */

    * COMPILE THIS ONCE;

    proc pmenu catalog=sasuser.pmenu;
      menu main;
         item 'File'   menu=file;
         item 'GENDER' menu=GENDER;
      menu GENDER;
         item 'Males'    selection=Males;
         item 'Females'  selection=Females;
         selection Males   "end;note;clear;include &pth\males.sas; notesubmit;";
         selection Females "end;note;clear;include &pth\females.sas; notesubmit;";
      menu file;
         item 'End';
    run;quit;

    * RUN THIS AS MANY TIMES AS YOU LIKE.
    * NO NEED TO RUN PMENU AGAIN;

    data _null_;
      window observe menu=sasuser.pmenu.main columns=65
        #5 @18 'Choose Male or Female Reports'
        #7 @18 'See options on top menu taskbar';
    display observe;
    run;quit;


    /************************************************************************************************************************/
    /*                                                                                                                      */
    /*    OUTPUT LOG AND LIST                                                                                               */
    /*                                                                                                                      */
    /*                                                                                                                      */
    /*    C:/UTL/MALES.LOG                                                                                                  */
    /*    ================                                                                                                  */
    /*    NOTE: PROCEDURE PRINTTO used                                                                                      */
    /*          (Total process time):                                                                                       */
    /*          real time 0.00 seconds                                                                                      */
    /*    2  proc print data=                                                                                               */
    /*    3  sashelp.class                                                                                                  */
    /*           (where=(sex='M'));                                                                                         */
    /*    4  Title "Males";                                                                                                 */
    /*    NOTE: There are 10 observations                                                                                   */
    /*       read from the data set                                                                                         */
    /*       SASHELP.CLASS WHERE sex='M';                                                                                   */
    /*    NOTE: PROCEDURE PRINT used                                                                                        */
    /*          (Total process time):                                                                                       */
    /*          real time 0.01 seconds                                                                                      */
    /*    5  proc printto;                                                                                                  */
    /*    6  run;                                                                                                           */
    /*    NOTE: PROCEDURE PRINTTO used                                                                                      */
    /*         (Total process time):                                                                                        */
    /*          real time 0.00 seconds                                                                                      */
    /*                                                                                                                      */
    /*    C:/UTL/MALES.LST                                                                                                  */
    /*    ================                                                                                                  */
    /*     Males                                                                                                            */
    /*                                                                                                                      */
    /*     Name    Sex  Age Height Weight                                                                                   */
    /*                                                                                                                      */
    /*     Alfred   M    14  69.0   112.5                                                                                   */
    /*     Henry    M    14  63.5   102.5                                                                                   */
    /*     James    M    12  57.3    83.0                                                                                   */
    /*     Jeffrey  M    13  62.5    84.0                                                                                   */
    /*     John     M    12  59.0    99.5                                                                                   */
    /*     Philip   M    16  72.0   150.0                                                                                   */
    /*     Robert   M    12  64.8   128.0                                                                                   */
    /*     Ronald   M    15  67.0   133.0                                                                                   */
    /*     Thomas   M    11  57.5    85.0                                                                                   */
    /*     William  M    15  66.5   112.0                                                                                   */
    /*                                                                                                                      */
    /************************************************************************************************************************/

    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
