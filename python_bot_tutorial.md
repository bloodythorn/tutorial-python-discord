# bot tutorial in python.

__version__ = 0.1.0

## 1.x setting up.

  Conventions:

  `thisisacommand to run`
  or
  `thisisafilename.py`

  ```
  This is a block of code.
  it is often multiline, and you can
    consider the margin where the triple ticks are
  ```

### 1.0 what you need.

  1. a computer that will run python.
  
  2. a text editor.
  
  3. basic computer knowledge: 
  
    * how to get to directories on your computer in a file explorer
  
    * how to open your cli, and get around at a basic level
  
    * an ability to find and follow instructions of the things i don't explain

  * note that knowing how to program isn't on here. come on, this is python peoples. knowing how to program will help, but this is really easy stuff.
  
  * if you are looking to learn to program, i will often tell you to use duck duck go (ddg) (or your search engine of choice) to find out how to do something. get used to doing this. if you have an issue self-learning, you need to correct that first. programming is creative and you should be able to want to do it enough to learn how to do the minor and common things on your own.
  
  * there's no mention of git. i struggled with this. as it's something i *always* use. if you don't use vcs software, you should. however every aspect of it is omitted from this unless it's a reminder to keep in mind for your vcs.
  
  - a quick note on terminology; being that i want to not wander a lot in this tutorial, i will be using terms that you might not know what they mean. don't worry about it if you don't. i am aware that i am not explaining these words, and i am trying not to use any that won't be explained in time, and it's not important that i do so. it will make this tutorial much more brief for now.
  
### 1.1 installing python.

  * link: https://www.python.org/downloads/
  
  * 3.5 or above please, preferably the latest, 3.9.1

  1. windows

    * use the windows app store,

    * or download the installer on the above site and run the exe

  2. linux

    * use your repo version (yay, apt-get, etc)

  make sure that the python binaries are in your path. meaning you can go to your operating system's cli, type these programs anywhere, and get similar results:

  ```
  maureen :: ~ » python --version
  python 3.9.1
  maureen :: ~ » pip --version
  pip 20.2.4 from /usr/lib/python3.9/site-packages/pip (python 3.9)
  ```

  * 'maureen' is the name of my pc, and '~'' is the directory i'm in. my home dir in linux.

  * you can see i am running python version 3.9.1, and pip, from the same version.

  * making sure the python binaries are in your cli's environment path is important for this to work.

  * *if* this doesn't work, there are bajillion tutorials you can find from a ddg search to learn how, and i am sure there are instructions on the python site.

### 1.2 installing a text editor.

  * a *text* editor, not a word processor. i don't want to waste your time explaining the difference (ddg)
  
  * otherwise it really doesn't matter.
  
  * sublime text is my editor dejure. it has a nag screen if you don't pay, so your choice.
  
  * since notepad, vi, nano, etc will all work. python costs nothing. so learning this is free save the required computer.

### 1.3 things to keep in mind.

#### 1.3.1 hosting the bot.

  * if you want your bot running 24/7, you'll need a computer to run it on 24/7.
  
  * we'll be making this bot in a manner in which you'll be able to  follow this procedure again on any other computer and setup this bot.
  
  * repl.it allows you to livehost a bot with a db, free and paid options.

  * *i* like to use tmux (or screen) which allows me to run a perpetual console command without being logged into console. i don't know the windows equivalent.

## 2.x setting up your environment.

### 2.0 getting comfortable.

  * a distraction free environment is very helpful.
  
  * only have up what you need. i have my editor, a cli window, and a web browser for reference. 
  
  * anything else i need, i bring up and break down as i need it, like a calculator (speedcrunch), etc.
  
  * if you're trying to get something done, sitting on discord is a bad idear. however for this, you'll need it.

  - summary: have up your text editor, cli, a web browser (so you can see this tutorial), and discord up and ready. get rid of everything else.

### 2.1 making a home for our new bot

  1. find a directory you want to contain your bot directory.
    
    * if you're in windows, you don't want to make this path too deep. there's a reason why most developer's apps for windows install themselves close to the root of c:.
  
  2. make a directory named what you want to name your bot.
  
    * make it simple yet descriptive, like the name of the project.
  
    * 'wiihacky' is the directory name for my main bot.
  
  3. go into that directory and lets create some project management files...

### 2.2 requirements.txt

  * this is a project management file that allows you to state up front what libraries your bot needs.
  
  * we will be needing at least one library directly, the python discord library(discord.py). 
  
  * anytime we install a library manually, we'll put it in here so it can be installed automatically.
  
  1. make a file in this directory called `requirements.txt`.
  
  * for now we'll leave it empty. i put this as a placeholder so i don't forget it later.
  
  - this is where you'll want to init your vcs, start putting in your list of ignored files and directories, etc. 

### 2.3 bot directory

  * the directory we're in won't have bot code, it's just for logistics files.
  
  * this includes any 'readme's you want to include, your vcs ignore file, licenses, project files, virtual environments, etc.
  
  1. make a directory called `bot`.
  
  2. in the `bot` directory make a text file called `__main__.py`.
    
    * this file must be named exactly as above.
    
    * python has special meanings for files, classes, functions, and variables that take this format, such as '__init__', and '__repr__'
    
    * in this case, its specifying the main entry point to our program. every program needs a place to start. this will be ours. Since we're making our bot in 'module' form, more on that later, we need that file in particular.
    
    * until future tutorials, this will be our only code file.

### 2.4 the 'hello world' of python

  1. open `__main__.py`
  
  2. on the first line type `print('hello suckers!')`
  
  3. go back to your cli from your root project botprojectname/ type the execution command `python -m bot`
    
    * we named the code directory 'bot' for a reason. this is it. shorter to type than your project name.
    
    * on its most basic level python is this easy. you direct it to a file, or in our case, a 'module' (the reason for the -m switch) and run it like a program. our module consists of an entry point file with one command in it.
    
    * 'print' is a python command. commands are reserved words and shouldn't be used for your own variable, function, and class names. more on that later.
    
    * 'hello suckers!' is what is called a 'string literal' you've literally typed a string in! rather than referring to it by a variable. string literals can be enclosed in both double and single quotes (and more) and tell python to interpret what is in-between as a printable string.
    
    * the parenthesis around the 'string literal' () is a mechanism in the programming language for encompassing both expressions, or in this case, a list of variables to pass on to the function.

### 2.5 the 'hello world' of the python logging library.

  1. open `__main__.py`
  
  * it's a good practice to use a logger, so lets include and init one.
  
  2. at the top of the document type `import logging as lg`
  
    * import is a way of pulling code from other locations and making it usable within your own code. you will be doing this a lot in most programming languages.

  3. a few lines below it put `log = lg.getLogger(__name__)`

    * note the python special identifier, '__name__'? it notes the name of the current running modules, which oddly enough should be '__main__'

  4. and a few lines below that, put `log.info('starting bot.)`

  5. run in your cli with `python -m bot`.
  
    * it won't print anything! why not?
  
  6. below that line type `log.error('hello suckers!')`. rerun it with the command in #5 and you'll notice you'll see it, but not the first one.
  
    * again, this is school, so i'd feel like i was lacking as an instructor if i didn't ask you why you think it does this?
  
  - logging allows different command levels. anything from information, to debug info, to warnings, errors, and critical failures. 
  
  - when a user is running your program, they certainly don't want to see all of the developer output.
  
  - however you will while you're writing your program. so we'll eventually make something to differentiate these conditions. till now, let's just set it up to dump out everything.
  
  7. in-between those two log commands, let's add a debug output. type `log.debug('testing this!')` in the middle of the other two, make a line if you need it.
  
    * you now know how to run your bot. don't be afraid to run it after every instruction (unless instructed not to) so you can see the results! do it now... nothing else? awww. only the error so far? that won't do.
    
    * also you can remove your 'print' statement from earlier. it's just gonna litter stuff up. or not. won't cause harm by leaving it.
  
  8. in between the import and the `log = lg.getlogger(__name__)` line, we're going to add all this:
  
  ```
  # create a template to make our logs look pretty!
  log_format_string = '%(asctime)s | %(name)s | %(levelname)s | %(message)s'
  log_format = lg.Formatter(log_format_string)

  # create the device that tells our log to output to the console stream.
  stream_handler = lg.StreamHandler()
  # set it to formatted to our template we created above!
  stream_handler.setFormatter(log_format)

  # grab the global log
  global_log = lg.getLogger()

  # make sure we see everything for everything
  global_log.setLevel(lg.DEBUG)

  # add our handler with our custom formatter
  global_log.addHandler(stream_handler)

  global_log.info('Global log setup!')

  ```

  * remember that my notes have these code lines indented. You should not be indenting anything yet. Python uses whitespace to deal with identifying different code blocks and scopes. So far everything we've been doing doesn't require any!
  
  * I also went ahead and documented the stuff I already wrote with simple but explanation comments. The comments start with a '#' and extend until the end of the line.
  
  * Good coders will use comments productively by explaining things they code that are hard to understand or follow, or just need some form of explanation. My comments for this project will be more excessive than it needs to be as I don't believe in commenting the obvious. And python is often very obvious.
  
  * If I don't have a place to report issues and TODOs, I also use comments for those. You'll see me use several comment tags, TODO, DEBUG, FIXME, NOTE. All of these tags in capital casing are meant to be temporary. Even if they end up not being.
  
  * Don't worry if you don't understand the formatting string template. Just remember that it uses what you give it to fetch information such as the time and date and other info and makes the output easy to read.
  
  - Running your bot now, you should now see all lines of output, including the time that each even fired, the log that fired it, the two being usually 'root' and '__main__', the severity of the log entry (info, debug, error, warning), and finally, your message.... hello suckers!

### 2.6 setting up the bot and connect it to discord.

  * First we're going to isolate the bot's environment so it won't pollute your python install.
  
  * Then we'll install our first external library, which will in turn probably install the next dozen or so external libraries it requires for you!
  
  * These environments have to be initialized each time open up a CLI right before you run your bot. It only goes away if you exit out of the CLI, or the activated python environment.

  * this allows you to make different python applications or bots and have different library requirements without each one getting in the way of each other, as they often do.

  1. Create a virtual environment by typing `python -m venv .venv`
    
    * We're running a python internal library 'venv' as if it were a program, and giving it the argument '.venv' as the name of our virtual environment directory which after you hit enter, you should notice it created.
    
    * the virtual environment needs to be activated before its used.
    
    * it contains everything your bot will need to run, once you've installed it.

  2. start the virtual environment by using the 'source' cli command that comes with python. so it will look like this: 
  
    `source ./.venv/bin/activate`

    * this is from the root of your project. Though you can activate it anywhere.
    
    * it should change your prompt in some way to signify that it's active. My promt adds a '(.venv)' to it. Don't run your bot unless you see this or any libraries you have in your venv that aren't installed in your root python install will error out.

#### 2.6.1 gaining your bot its credentials.

  * https://discord.com/developers/applications
  
  * You'll need to register a bot application, and obtain a secret key for it to logon.
  
  * I'm not going to walk you through this, but you need a Build-A-Bot token, it will be ~59 random low-end ascii characters, ie 0-9a-bA-B and some minor punctuation in one long string of characters.

  * ex: kt8ppHfpxj6ifjJzTv4fubyvSyzGS69GYXKih.YUfK5m3TdVoCuu,JmF.VE
  
  * The above is fake. Letting anyone gain access to your bots token is the same as giving login credentials for it. Keep it in a password manager with your other passwords.

#### 2.6.2 pip, installing libraries, and updating the requirements file.

  * first library we'll need will be discord.py, the python interface to the discord api.
  
  * It will certainly not be the last library we need.
  
  * pip is python's package system. It can usually find any additional features you need for python, assuming someone has written and published them.

  * for this, we'll need to go to the cli, and you need to have your environment activated (the (.venv) from earlier) to do this.

  1. type `pip install discord`
    
    * when its done it should have installed a host of different libraries. Near the end you should see "Successfully installed ..." with an entire list of libraries behind it.
    
    * Hey what's the deal? We only wanted one lib!
    
    * Take note of the discord.py it installed from this line, you'll need it to put in your reqs file. Mine looks like this: `discord.py-1.6.0`
  
  2. if you get a 'WARNING: You are using pip version ????; however, version ??? is available.' where the ??? are two different version numbers, you'll want to cut and paste the suggested text into your cli.
    
    * mine looks like this: `/home/thorn/Dropbox/dev/bot/tutorial/mybot/.venv/bin/python -m pip install --upgrade pip'`
  
  3. Any time you install a library, it means you require it. put it in your requirements.txt like this: `discord.py~=1.6.0`
  
    * this allows you to easily rebuilt the virtual environment for your program/bot. the command for installing all requirements would be `pip install -r requirements.txt` but we've already got everything installed in there...  

#### 2.6.3 That's all you need for your bot to login to discord.

  1. let us add the `import discord` to the imports at the top. Which will allow us to use the discord lib.

  2. At the top of your __main__.py document, below the import statements, let's put in our key as a string `secret_key = 'thisisthesecretkeyI.just.generatedonthediscordsite'`

    * Do I need to say put your own key in there? What I put up there won't work.
  
  3. At the very bottom of the file, insert this:

  ```
  # Create Bot
  wh = disextc.Bot()

  # Attempt to loin to discord
  log.info('Bot Starting...\nPress ctrl-c to stop.')
  wh.run(secret_key)
  ```

  * When you re-run your bot, you'll notice that it'll login to discord (so it tells you) and then just sit there until you press ctrl-c.
  
  * To see if the bot is actually on discord, you'll need to either read something from the main service, or join a guild/shard so you can see it login.
  
  * You can get the link to invite the bot to your discord developers portal. Goto the bot, click on the OAuth2 section, should be at the bottom.
  
  * You'll need to invite the bot to a discord server that you are also on to finish this tutorial. Discord will act as our interface to our bot.

## 3.x Getting your bot to do something, anything.

### 3.0 making some functions!
  
  * A bot runs asynchronously. This is a complex subject, and while I encourage you to learn more about python's asynchronous abilities, it won't be necessary to finish this tutorial.
  
  * So far we've used functions, but we have yet to define one.
  
  * asynchronous coding is known to have a more functional paradigm, meaning that it tends to rely on functions to alter and deliver information in stages, or functions. In a sequence, very similar to unix pipes, if you're familiar with them.
  
  * We're going to make two functions, one to be executed when the bot is online and ready, and another that will respond to us on discord.
  
  * If you don't have it up already: https://discordpy.readthedocs.io/en/latest/
  
  

## x.x constants

## x.x more on environments; environment variables

## x.x cogs/modules/extensions

## x.x database? Maybe?