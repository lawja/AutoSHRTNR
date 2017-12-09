# AutoSHRTNR
![alt text][logo]

[logo]: https://raw.githubusercontent.com/lawja/AutoSHRTNR/master/logo.png "Logo"

![Video Demo](https://giphy.com/gifs/3ohjV6XxCB65yVM9fG/html5)

AutoSHRTNR is a script that shortens links that appear on the clipboard using bit.ly's API
## Usage
To run the script, simply run

```shell
python3 autoshort.py
```
To continuously run the script as a daemon (background process), simply run

```shell
python3 autoshort.py &
```
This will output the PID so you can kill it by PID
```shell
kill {PID}
```
If you lose this PID you can kill it by
```shell
pkill -f autoshort.py
```
If you want to run the script from a shell alias I recommend to copy `autoshort.py` to `/usr/local/bin` with
```shell
cp autoshort.py /usr/local/bin/
```
And then create a shell alias by editing your .bashrc, .zshrc, or respective .rc by adding these lines
```shell
alias shrtn="python3 /usr/local/bin/autoshort.py &"
```
Then source your respective .rc with
```shell
source ~/.zshrc
```
Now you can invoke the autoshort.py with `shrtn`

## Install
To run this script you must have Python 3 installed, install from [here](https://google.com)
Once you have Python 3 installed you'll need to install the dependencies with
```
git clone https://github.com/lawja/AutoSHRTNR.git
pip3 install -r requirements.txt
export BITLY_TOKEN="{YOUR_KEY}"
python3 autoshort.py
```

## Setup
To use this script you must have a bit.ly account. Sign up for an account at [https://bitly.com/a/sign_up](https://bitly.com/a/sign_up).
After signing up, verify your email and navigate to *Menu > Options > Settings > Advanced Settings > API Support > Generic Access Tokens > Generic Access Token*

Then enter your password and export the access token as an environment variable, like so
```shell
export BITLY_TOKEN="{YOUR_KEY}"
```
I also recommend you add this to your respective .rc so the environment variable doesn't need to be constantly exported

## Limits
The bit.ly API has a call limit of 10,000 bitlinks per month, 1,000 calls per hour, 100 calls per limit
