losf
====
COMMAND

	lsof -i:8080
	lsof -i:8080
	lsof -sTCP:LISTEN -i:8080
	kill $(lsof -t -sTCP:LISTEN -i:8080)

iTerm

	> Profiles
	> Open Profiles
	> Edit Profiles
	> Keys
	> Global Shortcut Keys
	>  +
		> ^K
		> $(lsof -t -sTCP:LISTEN -i:)