# Create a Jupyter Notebook Server external connection with Ngrok Client
* When you are running your notebook server in local and aren't possible to open the port, you can use ngrok for making a connection from your local server to outsides.

## Using the Ngrok
- Join a site [https://ngrok.com](https://ngrok.com/) and download a ngrok.
  - You can create an external connection with a free account.
- Set up your local computer as the site tells you.

## Running through Tmux
- Tmux is a multiplexer which can manage multiple terminals and run background them.
- In Mac OS, Type `brew install tmux` for installing tmux.
  - If homebrew is not installed, install that first.
- To make a new session for jupyter, type `tmux new -s jupyter`.
- To run jupyter notebook, type `jupyter notebook`.
- The session can be detachable even in the running. Type `Ctrl + b + d`.
  - If you want to resume your session, type `tmux attach -t jupyter`
  - If you want to see your session list, type `tmux ls`
- To make a new session for Ngrok, type `tmux new -s ngrok`.
- You could make a connection with this command: `./ngrok http 8888`
- Save an address which a ngrok client created and detach the session.
