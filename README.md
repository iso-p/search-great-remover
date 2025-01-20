# search-great-remover
This repo shows how to remove the Search-great.com Redirect Virus. The way should be generally adoptable to other redict viruses.
Caution: the specific type of google account data loss is NOT verified. The user of the repo should verify this part himself/herself. At least for me, my google account history/bookmarks are not empty after the fix.


## Tutorial

**Step 1. Figure out the Chrome user data location**

Find out the directory where the user data of chrome is stored, for windows it should be

```shell
C/Users/<your_windows_user_name>/AppData/Local/Google/Chrome/User Data
```

For MACOS, it is located at

```
/Users/<your_mac_user_name>/Library/Application Support/Google/Chrome
```

**Step 2. Exit the Chrome browser**

**Step 3. Remove the virus**

Replace <the_chrome_user_data_location> with the location from step 1 and run the command below using the terminal (for Windows, WSL terminal is tested working fine):

```
find <the_chrome_user_data_location> -type f -exec grep -q "search-great" {} \; -exec rm -f {} \;
```

For removing other redirectory virus, the command might work as well. You will need to update the "search-great" to other keywords. But do not use keywords with many occurances to avoid removing everything.

**Step 4. Relaunch Chrome**

Since some user data is removed in the prev. steps, your google account should be signed out. While relaunching chrome and signing back in with your original account, please uncheck "Settings" in the chrome sync setting chrome://settings/syncSetup/advanced. Turning on sync for everything might cause the account to be re-infected by the virus.





