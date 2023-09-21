# Verifing Github Commits
## 1- Generating GPG key on your device ( using terminal )
[github-documentation](https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key)

-
      sudo apt install gpg
-      
      gpg --full-generate-key
-      
      gpg --list-secret-keys --keyid-format=long
-    
      gpg --armor --export {your_gpg_key}
      
      
## 2 - Telling Git about your signing key
[github-documentation](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key)

-      git config --global --unset gpg.format
-      gpg --list-secret-keys --keyid-format=long
-      git config --global user.signingkey {your_gpg_key_id}
-      git config --global commit.gpgsign true
-      [ -f ~/.bashrc ] && echo -e '\nexport GPG_TTY=$(tty)' >> ~/.bashrc
      
