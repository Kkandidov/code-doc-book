<details>
<summary>COMMON</summary>
  
  > Determine which shell you are using
  ```
  echo $SHELL
  ```
  > Set alias permanently (for example set 'k' alias for 'kubectl')
  ```
  echo 'alias k="kubectl"' >> ~/.zprofile
  source ~/.zprofile  
  ```
  
</details>

<details>
<summary>GIT</summary>

  > Set username and email for certain repo
  ```
  git config user.name "Your Name Here"
  git config user.email your@email.com
  ```
  
  > Set global username and email
  ```
  git config --global user.name "Your Name Here"
  git config --global user.email your@email.com
  ```
  
  > Show config settings for certain repo
  ```
  git config --list
  ```
  
  > Show config settings for certain repo
  ```
  git config --global --list
  ```
  
  > Remove the setting (for example username) from local .gitconfig
  ```
  git config --unset user.name
  ```
  
  > Remove the setting (for example username) from global .gitconfig
  ```
  git config --global --unset user.name
  ```
  
  > Delete object entirely (for example user) from local .gitconfig
  ```
  git config --remove-section user
  ```
  
  > Delete object entirely (for example user) from global .gitconfig
  ```
  git config --global --remove-section user
  ```
</details>

<details>
<summary>MAC</summary>

  > create a directory (for example ~/.nvm)
  ```
  mkdir ~/.nvm 
  ```
  
  > which ports are open on your Mac
  ```
  lsof -i -P | grep -i "listen"
  ```
</details>

<details>
<summary>NVM</summary>
  
  **Install NVM on macOS with Homebrew**

  > Update the Homebrew package list
  ```
  brew update 
  ```
  
  > Install NVM
  ```
  brew install nvm 
  ```
  
  > Create a directory for NVM at home
  
  ```
  mkdir ~/.nvm 
  ```
  
  > Edit the following configuration file
  ```
  vim ~/.zshrc
  ```
  
  > Add the below lines
  ```
  export NVM_DIR=~/.nvm
  source $(brew --prefix nvm)/nvm.sh
  ```
  
  > Load the variable to the current shell environment
  ```
  source ~/.zshrc
  ```
  
  > shaw available versions
  ```
  nvm ls-remote
  ```
  
  > Install node
  ```
  nvm install node
  ```
  > or (for example 14)
  ```
  nvm install 14
  ```
  
  > Verify what is installed with
  ```
  nvm ls
  ```
  
  > Set a version (for example 14)
  ```
  nvm use 14
  ```
  
  **Install autocannon**
  ```
  npm i autocannon -g
  ```
</details>
