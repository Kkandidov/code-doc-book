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

