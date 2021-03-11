# Making Pull Requests

Joining the group? Need to make a pull request to add your details to the "People" page?

First, clone the repository onto your computer. Using Terminal, navigate to the location you would like the repository to live, and run the following commands.

```
git clone https://github.com/HIRO-group/HIRO-group.github.io.git
cd HIRO-group.github.io
```

If you have SSH keys set up with GitHub, you can run the following instead.

```
git clone git@github.com:HIRO-group/HIRO-group.github.io.git
cd HIRO-group.github.io
```

Make your edits in a new Git branch. The following command will simultaneously create and switch to your new branch. Replace `<branch-name>` with your desired branch name, e.g. `add-alessandro`.

```
git checkout -b <branch-name>
```

Now, you can add your details to the file in at `./_data/people.yml`. Be sure to follow the existing format or you'll break things. Also be sure to add your photo to `./img/people/`. The picture needs to be square, and preferably not bigger than 400x400 pixels.

To save your changes, you need to use the `git add` command to tell Git to include your updates in the next commit. In the root directory of the repository, run the following commands (replacing `<image-name>` with the name of your photo).

```
git add ./_data/people.yml
git add ./img/people/<image-name>
```

Then, make the commit! Include a commit message with the `-m` flag. An example commit message is given below.

```
git commit -m "Add <name> to people page"
```

You're finally ready to push your changes to your very own remote branch! Run the following command with the same branch name you used above.

```
git push origin <branch-name>
```

You're almost done! Go back to the GitHub repository page, and there should be a button near the top of the page to open a new pull request.

If you'd like, after your pull request has been merged, you can delete the branch from your local repository.

```
git branch -d <branch-name>
```
