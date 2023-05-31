# savework
a simple script that just ... does what it says; creates a tgz of current work in a directory, restores it over top of anything that might be there, lists the saves.  Does not involve any version control shenanigans.  Of limited usefulness. DILUTE! DILUTE!

Usage: ./savework ...

  makes a tar archive of the current working directory and saves it in a directory one level up in the hierarchy; creates the directory if it doesn't exist.  pop does the obvious thing, deleting the saved version.  Be careful with this.  It's dangerous.
  list also does the obvious thing.  
  Examples:

λ ~/tms/ main* savework list
Saved states:
/Users/ngvrnd/saveWork_bkup/backup-tms-20230518190302.tar.gz (created at 2023-05-18 19:03:02)
λ ~/tms/ main* savework push
Pushed state: /Users/nicholascaruso/saveWork_bkup/backup-tms-20230531094750.tar.gz
λ ~/tms/ main* savework list
Saved states:
/Users/ngvrnd/saveWork_bkup/backup-tms-20230531094750.tar.gz (created at 2023-05-31 09:47:50)
/Users/ngvrnd/saveWork_bkup/backup-tms-20230518190302.tar.gz (created at 2023-05-18 19:03:02)
λ ~/tms/ main* savework pop
Popped state: /Users/nicholascaruso/saveWork_bkup/backup-tms-20230531094750.tar.gz
λ ~/tms/ main* savework list
Saved states:
/Users/ngvrnd/saveWork_bkup/backup-tms-20230518190302.tar.gz (created at 2023-05-18 19:03:02)
λ ~/tms/ main*
