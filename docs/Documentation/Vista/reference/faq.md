# FAQ

## Can I add a language to AskiaVista's interface?

The following procedure allows you to add a new language to askiavista's user interface. This consists of three steps:

### Select and copy a source language file

In order to add a new language, you need to translate the text in an existing language file. You can copy the existing file from the askiavista server to your local machine in order to facilitate this task.

*To locate the source language file:*

1.  On your askiavista server, open the following folder:
    `inetpub\wwwroot\AskiaVistaReader.Net4\Scripts\Locale\`
    In this folder, you will see certain files named `askiaVistaApp-LG.js` where `LG` corresponds to the two-letter language ISO code.
2.  Copy the file corresponding to the source language you want to translate from and paste it to your local machine.

!!! Warning
    Do not update the existing askiaVistaApp-LG.js files as they will be overwritten when askiavista is next updated.


### Translatethe user interface text elements

*To translate the user interface text:*

1.  Rename the file with the [appropriate language code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) (only use 639-1 ISO codes).
    For example, it would be named askiaVistaApp-es.js for a Spanish translation, askiaVistaApp-de.js for a German translation, etc.
2.  Open the file, and and enter translated texts accordingly.
3.  Save your file.

### Add the translation to askiavista

*To add the translated text to askiavista:*

1.  Check that you have renamed your file, using the appropriate language code (see above).

2.  Copy and paste your newly translated file back to the following folder:
    inetpub\\wwwroot\\AskiaVistareader.Net4\\Scripts\\Locale\\
3.  Log in to AskiaVista Admin (in askiavista version 5) and open `configuration`, then `language management`. There, add your new language.
4.  Open AskiaVista's SQL DB and open the `AV_Language` table.
5.  In the newly created row for your new language, add the appropriate two-letter language ISO code in the `TwoIsoLetter` field.

## Error codes

??? note "The following errors can be returned by a control for all methods:"
    
    | Code    | Description                                                         |
    |---------|---------------------------------------------------------------------|
    | `-100`  | The socket cannot be initialised.                                   |
    | `-102`  | The server did not reply.                                           |
    | `-103`  | The server did not reply correctly.                                 |
    | `-1006` | The survey is not ready.                                            |
    | `-1010` | The control AskiaVistaCtrl is not compatible with AskiaVistaServer. |

### -100

> ERR_SOCKET_NOT_READY
>
> Error when attempting to communicate with `AskiaVistaServer`

Check if there is already an instance of askiavistaserver.exe running                                                                                                          

### -101

> ERR_INIT_NOT_CALLED
>
> Init has not been called for this survey.

### -102

> ERR_NO_REPLY
>
> No reply from server.

Restart AVS service.                                                                                                                                                           

### -103

> ERR_WRONG_RESPONSE
>
> Server did not send the right reply.

### -104 

> ERR_PATH_NOT_SET
>
> The survey path has not been set.

### -105

> ERR_COUNT_NOT_SIZE_OF_ARRAY
>
> Parameters are not compatible.

### -106

> ERR_INCORRECT_RESPONSE
>
> The reply from the server was incorrect.

### -1001 

> ERR_NOT_OWNER_OF_RECORD
>
> An attempt was made to update a record belonging to another user.

### -1002

> ERR_INVALID_PROFILE
>
> The profile definition is incorrect.

### -1003

> ERR_DATABASE_ERROR
>
> Error while accessing the database.

### -1004

> ERR_NAME_CONFLICT
>
> There is a conflict; another object has the same name.

### -1005

> ERR_NO_RIGHT_FOR_APPLY
>
> The user does not have the right to save the object for his/her group/company.

### -1006

> ERR_SURVEY_NOT_READY
>
> The survey is not ready, probably after a communication break down.

AVS is most likely running in GUI mode and needs to be run in service mode.

On the server, close the window then in AskiaVista restart the service.

### -1007

> ERR_OBJECT_UNKNOWN
>
> The object is not known.

### -1008

> ERR_OBJECT_UNAVAILABLE
>
> The object is not available for this user.

### -1009

> ERR_INVALID_SURVEY
>
> The survey specified in the path is incorrect.

Check in askiaanalyse.

### -1010

> ERR_CONTROL_INCOMPATIBLE
>
> There is a compatibility problem between AskiaVistaCtrl and AskiaVistaServer.

The version of `AskiaVistaCtrl.dll` is likely out of date or out of sync, and needs to be updated.

### -1011

> ERR_INVALID_FIRST_QUESTION
>
> The first question is invalid.

### -1012

> ERR_INVALID_SECOND_QUESTION
>
> The second question is invalid.

### -1013

> ERR_CANNOT_PRODUCE_CALC
>
> The calculations could not be produced. Likely to be a Level problem.

### -1014

> ERR_CANNOT_READ_PACKAGE
>
> Cannot read the Package.

### -1015

> ERR_CANNOT_CREATE_FILE
>
> Cannot create the output file.

Check the server for disk space or corruption

### -1016

> ERR_WRITING_FILE
>
> Error while writing to the output file.

Check the server for disk space or corruption.

### -1017

> ERR_INVALID_FIRST_PROFILE
>
> Invalid definition of the first Profile.

### -1018

> ERR_INVALID_SECOND_PROFILE
>
> Invalid definition of the second Profile.

### -1019

> ERR_DATA_ERROR_FIRST_PROFILE
>
> Data error while reading the question in Row.

Indicates the system cannot find valid Response Tables. 

Check that the QES file functions properly in askiaanalyse

### -1020

> ERR_DATA_ERROR_SECOND_PROFILE
>
> Data error while reading the question in Column.

Indicates the system cannot find valid Response Tables. Check that the QES file functions properly in askiaanalyse

### -1021

> ERR_SCRIPT_SYNTAX_ERROR
>
> Syntax error in the script.

### -1022

> ERR_RESULT_EMPTY
>
> If no tables have been generated.

### -1023

> ERR_INVALID_THIRD_PROFILE
>
> Invalid definition of the third Profile.

### -1024

> ERR_DATA_ERROR_THIRD_PROFILE
>
> Data error while reading the question in Edge.

Indicates the system cannot find valid Response Tables. Check that the QES file functions properly in askiaanalyse

### -1025

> ERR_WEIGHTING_ERROR
>
> Error while calculating weighting.

### -1026

> ERR_UNKNOWN_COMMAND
>
> The command is not understood by the AskiaVistaServer.

### -1027

> ERR_NOT_AVAILABLE_IN_LEVEL
>
> Data not available in this Level.

### -1028

> ERR_SURVEY_ALREADY_LOADED
>
> Survey was already loaded.

### -1029

> ERR_CANNOT_READ_DATA
>
> Error while reading data.

### -1030

> ERR_QUESTION_TYPE_INCOMPATIBLE
>
> The question type is not compatible for the query.

### -1031

> ERR_NOT_IMPLEMENTED
>
> Method not implemented by server (version problem).

### -1032

> ERR_TIME_OUT_IN_LOCK
>
> Time-out while waiting for response server-side.

### -1033

> ERR_NO_LICENSE_FOR_TABS

### -1034

> ERR_INVALID_LEVEL

### -1035

> ERR_SURVEY_NOT_LOADED
>
> The survey is not ready yet.

The survey may still be loading (especially QEWs with many waves). Check the CPU usage of AskiaVistaServer in Services Management. It should be at 0 when the survey is ready.

### -1036

> ERR_NOT_ENOUGH_INTERVIEWS


### -1037

> ERR_CANNOT_FIND_EIGENVALUES

### -1038

> ERR_MEMORY_ERROR

### -1039

> ERR_CANNOT_RELOAD_DURINGINVERSION
>
> It is not possible to reload a survey while an inversion is being carried out.

Wait for the inversion to finish before reloading the survey.

### -29000

> ERR_
>
> Cannot initialize AskiaVistaServer controls.

Restart the AVS service.
