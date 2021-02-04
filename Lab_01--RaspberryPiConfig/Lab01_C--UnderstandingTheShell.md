# Bioe 421/521: Microcontroller Applications
#### Instructor: Jordan Miller<br>TA: Adam Farsheed<br>github.com/jmil/Bioe421_521-MicrocontrollerApplications

## Lab 1C. Understanding the Shell



From [Wikipedia, Shell (computing):](https://en.wikipedia.org/wiki/Shell_(computing))
> A shell manages the user–system interaction by prompting users for input, interpreting their input, and then handling an output from the underlying operating system.

##### The text-only command-line interface (CLI), commonly shortened to "command-line", is the simplest shell we will use in class.

Command-line utilizes a keyboard and video screen as the human-computer interface. It is also known as a terminal (think of the very ends of the cables connected to the computer), or shell (think of a wrapper -- a shell is a program which wraps or compartmentalizes **YOUR interface** with the computer and allows you to run commands and programs).
	
As we've seen, you typically get a blinking prompt where you can enter commands, you submit the commands by typing `<enter>`. Often you will get text sent back to you by the shell as the output of your command.

The string of characters next to your blinking cursor is called the command prompt. It is the computer asking you for input in the form of a command and syntax that it has been programmed to recognize. Default on Pi for the command prompt is to show your username, the '@' symbol, and your short hostname, followed by the (abbreviated where possible) current directory in which your shell is located:

	pi@raspberrypi ~ $ _
		
The default command prompt will show a dollar sign (`$`) if you are a regular user, and a pound sign (`#`) sign if you are a superuser. We'll get to explain the superuser later.

One of the most important aspects of the shell, especially for new users, is that it has built in help files. You access help files for a given command using the `man` command. As an **argument** to this command, you need to submit the name of the command whose manual pages you would like to lookup, and then press **<enter>** to submit your command for processing. Thankfully, the `man` command has it's own helpfiles. Let's read them.

1. Using the command prompt, bring up the manual pages (often abbreviated as the "man pages") for the `man` command itself:

		$ man man

	The screen will be cleared and you will be presented with the manual. Note that the manual continues off the screen. For getting help on using man pages, use the **`<h>`** key ("h" for "help"). To scroll down one line at a time, use the **`<enter>`** key. To scroll down one entire page at a time, use the **`<spacebar>`**. To go to the previous page, press the **`<b>`** key ("b" for 'back'). To exit out of the man pages, press the **`<q>`** key ("q" for 'quit').
		
	##### NOTE: Many man pages have a very helpful section way at their bottom entitled "EXAMPLES". This section often shows written commands with their explained output. Very handy!	
	
## Assignment


1. Read some more man pages (for the programs listed below), and take detailed notes. **DO NOT** copy the man pages verbatim; instead, use your own words. Use the Markdown format since it can be read easily by humans and easily converted into HTML by computers for nice rendered viewing online.

	On the Windows computer next to your Raspberry Pi, have your lab partner use the free editor with live rendering at:
	http://dillinger.io
	You can link it to google drive, dropbox, and github. Or you can edit and download the file.
	### CRITICAL NOTE: Anything you save to the desktop on the Windows computer will be deleted after you logout (Rice IT default setup for the Windows computers). So it's best to use online text editing to save your file. Email it to yourself for now so that you have a backup.
	
	### TIP: Be descriptive here, the document you write will be available to you and your partner during the upcoming quiz.


	Write down general and specific usage notes about each command using Markdown format (*.md). The markdown format allows you to do hierarchical text formatting with only a few extra characters. Feel free to use a web browser on the neighboring PC to help you work through understanding these programs and how they are commonly used:

		man
		apropos

		id
		w
		who
		whoami
		hostname
		passwd
		sudo
		su
		ps
		top
		uptime
		
		echo
		touch
		chown
		chmod
		chgrp
		adduser
		userdel
		addgroup
		crontab
		nano
		
		pwd
		ls
		dir
		mkdir
		cd
		
		cp
		mv
		rm

		bash
		dash
		sh
		ssh
		sshd
		which
		clear
		
		cat
		sed
		grep
		more
		less
		head
		tail
		
		tar
		unzip
		wget
		curl
		ifconfig
		mount
		ping
		apt-get
		git
		python
		raspistill
		raspivid
		uname
		
		reboot
		halt
		poweroff
		shutdown

	**TIP** from: http://unix.stackexchange.com/questions/205464/whats-the-difference-between-poweroff-and-halt
	
	> `halt` terminates all processes and shuts down the cpu.
	
	> `poweroff` is exactly like `halt`, but it also turns off the unit itself (lights and everything on a PC). It sends an ACPI command to the board, then to the PSU, to cut the power.
	
	> `shutdown` is like poweroff, but it also runs the shutdown scripts.
	
	**NOTE** for the purposes of our class and the Raspberry Pi: `halt`, `poweroff`, and `shutdown` will essentially achieve the same goal, but these aliases help with backward compatibility with programs from other *NIX systems (Unix, Linux, OpenBSD, etc.). We will generally prefer using the `shutdown` command because it's a bit cleaner and nicer to your system.


		
		
1. Using your notes, answer the following questions. In your answers **be sure to indicate** the command(s) you used to arrive at your answer. One lab partner should run the Pi while the other helps advise using the notes you generated. Switch roles mid-way through these questions so you each get a feel for the terminal.

	1. What is your username?
			
			:

	1. What is your short hostname?

			:


	1. What command can you use to find your IP Address? Using this command, what is your inet?		

			:


	1. What is the full path of your current working directory?

			:


	1. How long has your Pi been turned on?
	
			:


	1. What version of `python` is installed on your Pi?
	
			:


	1. How long does it take to get a `ping` from google.com? How many bytes did you get back? NOTE: you can quit pinging with **`<ctrl-C>`**
				
			:


	1. Where is the `man` command located on your hard drive?
			
			:


	1. What is the model name of your processor? (hint: it's stored in the `/proc/cpuinfo` file)
			
			:

	1. What version of Raspbian Linux are you running on your Pi? (hint: it's the "pretty name" shown in the `/etc/os-release` file)

			:

	1. You want to create an empty txt file called “ILoveRice.txt”. What command can you use to do this? You come out of a very hard midterm and want to delete this file. What command can you use to do so?

			:


	1. What command will let you reboot the Pi immediately?

			:


	1. What percentage of the CPU does the `top` command utilize?

			:



## Shutdown Procedure

1. Shutdown your Pi properly:

		$ sudo shutdown -h now

 Unplug everthing and restore the Windows desktop computer to a working state.

### Make sure you show your work to an Instructor before you leave for the day.

