# LT Courses Code Repository
Source code of projects related to courses taught by LT (also student projects).

In general consider to add projects as _git submodules_. Submodules appear as folders in the git repository hierarchy (although with a changed icon in github) and refer to other git repositories (which might even be private).

## Working with submodules using `watson_speechandtext_demo` as example:

goal: have `remstef/WatsonSpeechTextDemo` as a submodule in `tudarmstadt-lt/courses/qa-examples/watson_speechandtext_demo`

1. clone `tudarmstadt-lt/courses` repository 
    ```
$ git clone https://github.com/tudarmstadt-lt/courses.git courses-lt
    ```

2. add submodule
    ```
courses-lt/qa-examples$ git submodule add https://github.com/remstef/WatsonSpeechTextDemo.git watson_speechandtext_demo
    ```
    
3. within the submodule folder everything is standard git and refers to the remote repository of the submodule, e.g. `git pull`, to update the contents from `remstef/WatsonSpeechTextDemo` or `git commit` and `git push` to push edited content to `remstef/WatsonSpeechTextDemo`.

4. sync new content from the submodule's repository with the main repository (pull changes, commit updates, push changes)
    ```
courses-lt/qa-examples/watson_speechandtext_demo$ git pull
courses-lt/qa-examples$ git commit watson_speechandtext_demo -m 'updated submodule'
courses-lt/qa-examples$ git push
    ```

### Notes
- When you clone `tudarmstadt-lt/courses`, the submodules are not cloned, they appear as empty folders. Run the following commands to pull the content: 
    ```
$ git submodule init
$ git submodule update
    ```

  Alternatively you can add the `--recursive` switch to the `git clone` command in order to tell git to checkout also the submodules.
    ```
$ git clone --recursive https://github.com/tudarmstadt-lt/courses.git courses-lt
    ```

- Find further information on submodules here: https://git-scm.com/book/en/v2/Git-Tools-Submodules
- **In any place of the hierarchy, type `git remote -v` in order to see the remote path of the current git related commands!**
- For an overview of submodules in check `.gitmodules` file in the root directory of the repository
