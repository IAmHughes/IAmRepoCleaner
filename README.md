# IAmRepoCleaner

### NAME:
repo-cleaner - Deletes every repository for the user or org specified up to 30 at a time

### SYNOPSIS:

```
repo-cleaner [-o=<org_name>] [-u=<username>] [-s=<string-to-match-against]
```

### DESCRIPTION:
Deletes every repository for the user (if `-u=<username>` is used) or for an organization (if `-o=<org_name>` is used instead) that matches the string (specified by `-s=<string-to-match-against>`). Will delete up to 30 repositories with every execution.

### OPTIONS:
**--org**
**-o**
When running the tool, this flag sets the API endpoint to point to an organization (specififed by -o=<org_name>), deleting the repos that match the given string from -s (see below).
* _NOTE:_ Can NOT be used with the -u option.

**--user**
**-u**
When running the tool, this flag sets the API endpoint to point to a user (specified by -u=<username>), deleting the repos that match the given string from -s (see below).
* _NOTE:_ Can NOT be used with the -o option.

**--string**
**-s**
When running the tool, this flag sets the string to match against the name of the repo(s) you are wanting to delete.

### EXAMPLES:
* Deletes repos under org "TheBeardedTom" that are named "Test_Repo_*" - For example, Test_Repo_, Test_Repo_qa, Test_Repo_234, etc.

```shell
bash repo-cleaner -o=TheBeardedTom -s=Test_Repo_
```

* Deletes repos under user "IAmHughes" that are named "MyRepo*" - For example, MyRepo, MyRepo1, MyRepo99, MyRepoQA, etc.

```shell
bash repo-cleaner -u=IAmHughes -s=MyRepo
```

### API DOCUMENTATION:
All documentation can be found at https://developer.github.com/v3/
