# Prototypes
All testing stage projects before pushing to main branch of BTQAD-Automation repo.

https://hackanva.github.io/Prototypes/eggplant_tutorial.html




(* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *
HAKAN'S VERSION
* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *)
//Log into Agility
DoubleClick "Chrome/GoogleChrome"
Click {Image:"vawwinsidervagov", WaitFor:4}
TypeText "https://www1.dfrhost.com/va-fsc-gov/Default.aspx?menu=RegressionTestPage",Return
Click {Image:"PIVSignIn_002", WaitFor:20}
Click {Image:"CertificateOKButton_002", WaitFor:10}
WaitFor 10, "PINEntry_002"
Click {Image:"PINEntry_002", WaitFor:4}
TypeText "270607",Return

//In Agility
WaitFor 10, "SearchIcon"
Click Image:"SearchIcon"
TypeText "S-124488",Return
Click Image:"StorySearchResult"
// Set imagefound location to status
Set the assertionBehavior to "Warning"
Assert that ImageFound(Image:"StatusAccepted", WaitFor: 10) or ImageFound(Image:"StatusDone", WaitFor: 10)

DoubleClick Image:"UserStoryTitle"
TypeText ControlKey, "a"
TypeText ControlKey, "c"
wait 2
put RemoteClipboard() into userStoryTitleText
if userStoryTitleText is not empty then
	log " userStoryTitleText: " & userStoryTitleText
else
	log "User Story Title text could not be retrieved."
end if


DoubleClick Image:"Definition_Done_003"
TypeText ControlKey, "a"
TypeText ControlKey, "c"
wait 10
put RemoteClipboard() into def_done_text
if def_done_text is not empty then
	log"Definition of Done text: " & def_done_text
else
	log"Definition of Done text could not be retrieved."
end if


DoubleClick Image:"Description_1"
TypeText ControlKey, "a"
TypeText ControlKey, "c"
wait 10
put RemoteClipboard(5) into DescriptionText
if DescriptionText is not empty then
	log " DescriptionText: " & DescriptionText
else
	log "DescriptionText could not be retrieved."
end if


DoubleClick Image:"AcceptanceCriteriaBacklog"
TypeText ControlKey, "a"
TypeText ControlKey, "c"
wait 2
put RemoteClipboard() into AcceptanceCriteriaText
if AcceptanceCriteriaText is not empty then
	log "AcceptanceCriteriaText: " & AcceptanceCriteriaText
else
	log "AcceptanceCriteriaText could not be received. "
end if



