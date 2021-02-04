# Bioe 421/521: Microcontroller Applications
#### Instructor: Jordan Miller<br>TA: Adam Farsheed<br>github.com/jmil/Bioe421_521-MicrocontrollerApplications


## Lab 2B. Customizing Your Command Prompt

### A Note about Your Shell History

From: http://www.raspberrypi.org/documentation/usage/terminal/README.md
		
> HISTORY AND AUTO-COMPLETE
> Rather than type every command, the terminal allows you to scroll through previous commands that you've run by pressing the **`<up>`** or **`<down>`** keys on your keyboard. If you are writing the name of a file or directory as part of a command then pressing **`<tab>`** will attempt to auto-complete the name of what you are typing. For example, if you have a file in a directory called **_aLongFileName_** then pressing **`<tab>`** after typing **_a_** will allow you to choose from all file and directory names beginning with **_a_** in the current directory, allowing you to choose **_aLongFileName_**.		
		

### The Command Prompt

As we learned last time, when you login you are presented with the command prompt:

		pi@raspberrypi ~ $ _

Here we will see where the instructions for how to display the command prompt are located, and you will work to customize your prompt to be more informative.


Look at the contents of your `.bashrc` file located at `/home/pi/.bashrc`. This is the configuration file for your login. We can customize your command prompt by editing this file.

	$ cd ~
	$ pwd
	$ ls -la
	$ cat ~/.bashrc
	
The lines that start with a **`#`** are comments, made for humans to read and ignored by the computer. You can make comments for yourself in this file **one line at a time** by starting the line with the **`#`** character. The computer will ignore everything on that text line. If you have a command you want to temporarily disable, you can simply append the **`#`** to the beginning of that line of code to "comment it out"; you have effectively turned the line of code into a comment so it will be ignored by the computer, and therefore disabled.

Using the `cp` command, let's make a backup of this file. That way if we make a mistake we should be able to revert it.

	$ cp ~/.bashrc ~/.bashrc-BACKUP

Check that your backup file is there, and that it's contents are correct. What commands did you use?

	$
	$


## Assignments


1. Now we will use `nano` to edit the `.bashrc` file and change the command prompt.

		$ nano ~/.bashrc

	Scroll down to put the cursor just **BETWEEN** these two lines:
	
		...
		esac

		# enable color support of ls and also add handy aliases
		...
	

	The following shows some text we want to insert into our `.bashrc` file to make an awesome command prompt. And, hat-tip to the source Matthew Holt for this awesome command prompt code:

		...
		esac

		Decoration1="\[\e[90m\]╔["
		RegularUserPart="\[\e[36m\]\u"
		RootUserPart="\[\e[31;5m\]\u\[\e[m\]"
		Between="\[\e[90m\]@"
		HostPart="\[\e[32m\]\h:"
		PathPart="\[\e[93;1m\]\w"
		Decoration2="\[\e[90m\]]\n╚>\[\e[m\]"
		case `id -u` in
		    0) export PS1="$Decoration1$RootUserPart$Between$HostPart$PathPart$Decoration2# ";;
		    *) export PS1="$Decoration1$RegularUserPart$Between$HostPart$PathPart$Decoration2$ ";;
		esac


		# enable color support of ls and also add handy aliases
		...

	However, you may notice some characters that will be very difficult to type:

	So, here's a shortcut to do this a bit faster. Follow **carefully**: Let's use the `wget` command to grab this text snippet from the `.md` file on github **for this lab,**. **Hint:** You may want to use a URL shortener such as:

		http://tinyurl.com/421-CommandPrompt
	
	So then you might do something like:

		$ wget -qO- http://tinyurl.com/421-CommandPrompt > commandprompt.txt

	Next, use `nano` to edit this new `commandprompt.txt` file and delete everything except this text snippet. Then insert it into your `.bashrc` file using `<ctrl-R>` from within a new `nano` editor.

	Here we see that variables can be created by starting a line with a variable name, then assigning a value to it with the `=` sign. We later can call the value of this variable by using the `$` sign before the variable name (which you see down where it says `export PS1=`).
 
	 To see the changes in your command prompt, you need to logout and then login again. This will cause the `~/.bashrc` file to be read back in. You can logout with:
 
		$ exit

	After you login again, write down what your new command prompt looks like:

		:
		:
		:
 

1. Make backups of your edits in case you type something incorrectly along the way. What command do you use to backup this file?

		$

1. Next, edit the command prompt and customize it to show your name (or a creative name). write down what your new command prompt looks like:

		:
		:
		:
 
1. Now, let's do something more complicated -- we want our command prompt to show the current time. So each time `$PS1` is called, we want the current time to be updated. Check out the BashRCGenerator to help you customize your prompt:
http://bashrcgenerator.com/

	Update your command prompt with the current time and some custom colors for your team name or other sections.
 
	To add other commands here into your prompt, you might consider using the backtick ``` ` ``` character, which is located just under the **`<esc>`** key on your keyboard. Backtick escapes you into it's own temporary shell mid-stream, and takes the **STDOUT** from that command to insert. For example, in the line:
 
		case `id -u`

	The shell effectively runs `id -u`, and sends the output from this command to the `case` operator in this line for evaluation. It's a simple way to have nested commands simply by encasing your command within some backticks. What do you get when you run `id -u` from the command line? Check the man page for the `id` command to learn more.

	Write down what your new command prompt looks like:

		:
		:
		:

	 	

Show your new command prompt to your Instructor!
 
