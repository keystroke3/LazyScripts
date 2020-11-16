# LazyLorem

This is a tool to generate filler text for whatever case during design.  
It picks words at random from a large snippet of Lorem Ipsum and saves them to clipboard and outputs them to standard out.

## Installation
### Requirements
* Python >= 3.0
* Linux
* xclip


### Install as system command
The script is a single python file and can be installed simply by copying the contents of the file  
and putting n a directory that is in system PATH like `/usr/bin/`.

#### Single line
Using curl:
`sudo curl  
 https://raw.githubusercontent.com/keystroke3/LazyScripts/main/LazyLorem/lazylorem >> /usr/bin/lazylorem && sudo chmod +x lazylorem`  
or wget:  
`sudo wget https://raw.githubusercontent.com/keystroke3/LazyScripts/main/LazyLorem/lazylorem -O /usr/bin/lazylorem && sudo chmod +x lazylorem`

#### Git clone
With this method, you have to clone the repo and create a symbolic link in `/usr/bin/`
```bash
git clone https://github.com/keystroke3/LazyScripts.git
cd LazyScripts/LazyLorem
chmod +x lazylorem
ln -s $PWD/lazylorem /usr/bin/
```
To use it, just run `lazylorem` from anywere in the terminal. You can also use it with list selectors and command runners such as [rofi](https://github.com/davatorium/rofi) and [dmenu](https://github.com/davatorium/rofi)
### Use with python command
You can decide you don't want the script to be installed as a command. In that case you can clone the repo and run the script directly
```bash
git clone https://github.com/keystroke3/LazyScripts.git
cd LazyScripts/LazyLorem
python3 lazylorem
```

## Usage
The script takes 0 - 2 arguments like so:   
`lazylorem [WORD_LIMIT] [LINE_LIMIT]`  
If run with no arguments, it will print 5 random lorem ipsum words in one line. The arguements can be passed as follows:

| Word Limit     | Line Limit     | Outuput     |
| :------------- | :----------: | :----------- |
|  - |  - | The default number of words in 1 line    |
| 1   | - | 1 random word in 1 line |
| -   | 2 | This is treated as  `lazylorem 2` |
| 3   | 2 | 2 lines with 3 random words each |
| r/R   | 2 | Random number of words spanning 2 lines |
| 2   | r/R | A random number of lines each with 2 random words |
| r/R   | r/R | A random number of words in a random number of lines |

