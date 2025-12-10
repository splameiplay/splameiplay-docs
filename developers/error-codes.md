# Error Codes

{% hint style="info" %}
This page is only intended for those with knowledge of programming. If you are a user of SplameiPlay, check out the user [troubleshooting page](../users/troubleshooting.md)
{% endhint %}

## 0\_DESERIALIZE\_FAILURE (0x001)

This error occurs when SplameiPlay failed to deserialize the save file for itself, the network client or for recap. This is an unrecoverable error and SplameiPlay will not be able to continue.

### Cause

When SplameiPlay boots, it will open the save files for itself, recap and the network client and retrieve their data in bytes. Once done, it will deserialize the data so SplameiPlay can retrieve their values. This exception occurs when SplameiPlay was unable to retrieve these values. Typically because the save file was corrupted.

### Possible fixes

Because this error is likely caused by a corrupt save file, the only fix would be deleting the save file that can be found in `%appdata%/Splamei/SplameiPlay/Saves`

## 0\_SERIALIZE\_FAILURE (0x002)

This error occurs when SplameiPlay failed to serialize one of the save files during the save process. This is an unrecoverable error and SplameiPlay will not be able to continue.

### Cause

During the save process, SplameiPlay will serialize the save data into bytes to be saves. This exception will occur when SplameiPlay failed to serialize the data for the save file. This likely occurs due to saving a corrupt save file

### Possible fixes

Because this error is likely caused by a corrupt save file, the only fix would be deleting the save file that can be found in `%appdata%/Splamei/SplameiPlay/Saves`

## 0\_SAVE\_FILE\_404 (0x003)

This error occurs when SplameiPlay get's an unknown error while checking for the existence of the save file

### Cause

If SplameiPlay has an exception during the checking process of save files, this exception will occur. The exact cause is unknown

### Possible fixes

Due to this being an unknown exception, there is no full proof fix. Deleting the save file may fix the problem or restarting / reinstalling SplameiPlay

## 0\_INDEX\_DESYNC\_ERROR (0x004)

This error occurs when the list indexes in the save systems used within SplameiPlay are not the same length. This is an unrecoverable error and SplameiPlay will not be able to continue.

### Cause

SplameiPlay has lists knows as the index. These combination of lists store data needed for SplameiPlay. When these list get different counts, SplameiPlay has to stop running as one or more of the lists has become corrupted and if SplameiPlay kept running, issues would occur with SplameiPlay attempting to retrieve a value outside the range of the list or data would be ignored.

### Possible fixes

When this exception occurs, SplameiPlay automatically clears the offending index lists and will show the error screen. Because of this, usually, no extra action is required but you may need to delete the save file if this issue continues to occur

## 3\_EXTRACTION\_EXCEPTION (0x005)

This error occurs when an exception is caught during the extraction process when installing a project. This error will stop installing the project but SplameiPlay will continue to run

### Cause

During the installation process when adding a project in SplameiPlay, an exception may occur while extracting the zip file. This may occur due to a corrupt zip file or an error saving the uncompressed files.

### Possible fixes

If you still receive this error when trying again, try reinstalling SplameiPlay or changing where SplameiPlay will store projects. If you still receive this issue, the zip file is corrupt so you'll need to contact the publisher to fix the file.

## 4\_SPINSTALLER\_PARSE\_EXCEPTION (0x006)

This error occurs when there was an error while parsing the data from an `.spinstaller` file. This exception is recoverable and will not cause SplameiPlay to fail.

### Cause

This exception occurs when SplameiPlay failed to parse the data given within an `.spinstaller` file. This error typically occurs when the data provided within the file is invalid and so, SplameiPlay cannot understand it

### Possible fixes

Make sure the syntax of the file is correct and that SplameiPlay has the permission to access the file. If this exception still occurs, try reinstalling SplameiPlay

## 0\_PAGE\_SETUP\_EXCEPTION (0x007)

This error occurs when SplameiPlay failed to decode the data of a custom project when showing its project page. This is an unrecoverable error and SplameiPlay will not be able to continue.

### Cause

This exception occurs when SplameiPlay is loading the saved data in the index that contains the data for custom projects. If SplameiPlay failed to decode this data, it will trigger this exception and stop running. This is commonly caused due to SplameiPlay trying to load corrupt data within the index.

### Possible fixes

Try reopening the project page but if this exception continues to occur, the index has become corrupted. You'll needed to delete the main save file and try again.

## 1\_PROJECT\_UNINSTALL\_EXCEPTION (0x008)

This error occurs when SplameiPlay failed to Uninstall a project when requested too. This is a critical exception however, SplameiPlay can recover.

### Cause

This exception will occur when SplameiPlay attempts to uninstall a project. SplameiPlay will remove all references (except from recap) of the project from the index and delete all the files for the project that SplameiPlay manages. Sometimes this may fail when the files no longer exists because of their removal during runtime or a corrupt save file.

### Possible fixes

Firstly, restart SplameiPlay to see it it realises the absence of the project. If the exception continues to occur, the save file's index may have become corrupted. In this case, you'll have to delete the save file.

## 4\_FILE\_LAUNCH\_EXCEPTION (0x009)

This error occurs when SplameiPlay failed to launch the project requested to be started by the user. This is a non-critical error so SplameiPlay will continue to run however, it will not launch the project.

### Cause

When SplameiPlay attempts to launch a project, it will launch the file that it is told to run. This exception will occur when the process of running the file failed. Typically due to the file not existing.

### Possible fixes

Make sure the executable file SplameiPlay runs does exist and that your user and SplameiPlay has the permissions to launch the file. SplameiPlay may also need to be updated or re-installed. If the exception continues, try deleting the save file or re-installing the project.

## 4\_FILE\_LAUNCH\_EMPTY (0x00A)

This exception occurs when SplameiPlay can't start the project due to the file that need to be run not existing. This exception won't cause SplameiPlay to close but it won't be able to launch the project.

### Cause

If the location provided within the save file index is incorrect, when SplameiPlay attempts to launch the faulty project, it will be unable to file the file to be opened. SplameiPlay performs checks when starting to ensure that the index locations are correct so this error is likely due to the files being deleted at runtime.

### Possible fixes

Restart SplameiPlay to allow it to perform the location check for the project to be automatically removed if still faulty. Also verify that no other process is deleted the files that SplameiPlay is using.

## 4\_SPTHEME\_PARSE\_EXCEPTION (0x00B)

This is caused when SplameiPlay failed to parse the data of an `.sptheme` file. This is not a critical error so SplameiPlay will continue to function.

### Cause

This exception is typically due to an incorrectly created theme file where the syntax within at least one of the lines is incorrect

### Possible fixes

Verify the syntax of the lines within the `.sptheme` file and hex code to make sure they are correct. Sometimes, SplameiPlay may be too new or too old so it's best to update the theme file and SplameiPlay to the lates versions.

## 0\_POLICY\_FILE\_EXCEPTION (0x00C)

This occurs when SplameiPlay failed to get a policy file to be used. Because SplameiPlay requires a policy file to be active, this is an unrecoverable error and SplameiPlay will be forced to close.

### Cause

When SplameiPlay is doing it's initial read of a `.splameiplay` policy file, if it is unable to get it's file version, type or if it's a 'hopping' policy file.

### Possible fixes

This is likely due to an incorrectly set up policy file so check to make syntax of the policy file is correct and that SplameiPlay can read from it.

## 0\_POLICY\_HOP\_LOOP (0x00D)

This exception occurs when SplameiPlay fails to get a correct policy within enough iterations. Because SplameiPlay needs a policy file once it's got an initial file, this error is not recoverable.

### Cause

Once SplameiPlay has requested for 50 files for a policy and all files request SplameiPlay to 'hop' to a new file, SplameiPlay will detect that a 'Policy Hop Loop' is occurring so will terminate the policy.

### Possible fixes

Make sure that SplameiPlay can access the policy with as little 'Policy Hops' as possible and verify that all policy files SplameiPlay will access do not lead to SplameiPlay returning to a previous policy file.

## 0\_INCORRECT\_POLICY (0x00E)

Occurs when SplameiPlay fails to read the policy file when in it's 'policy applying' stage. This error is unrecoverable since SplameiPlay required a valid policy file.

### Cause

If SplameiPlay fails to read the policy file due to an invalid syntax or unknown policy term, SplameiPlay will be unable to decode and parse the policy file. The policy file may also be rejected by SplameiPlay if it uses an incompatible version.

### Possible fixes

Verify the syntax of the policy file and make sure any text that should be ignored starts with `-` to make it a comment. Also make sure that the policy file and SplameiPlay are at their latest version to make sure they are compatible.
