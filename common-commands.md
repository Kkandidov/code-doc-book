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

</details>

