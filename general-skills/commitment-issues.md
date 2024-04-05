# Commitment Issues

Hint 1: Version control can help you recover files if you change or lose them!

Hint 2: Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#\_git\_version\_control)

Hint 3: You can 'checkout' commits to see the files inside them

Looking at the title of the challenge and the hints, we can tell that the challenge involves recovering files from git repositories. The challenge file most likely also contains a repository, so let's first grab the file using our environment and take a extract it.&#x20;

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>Grabbing the zip file for the challenge and extracting it</p></figcaption></figure>

As we can see above from the extracted files list, my suspicions were correct and there is indeed a Git repository in this folder.

Now, we can move into the extracted "drop-in" directory (using the `ls drop-in` command) and look at the file and reinitialize the Git repository inside.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption><p>Reinitializing the git repository</p></figcaption></figure>

We can now run `git log` to try and see the history for the repository. We can find this command by just making a quick google search:&#x20;

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption><p>Searching for the "git history" command on Google</p></figcaption></figure>

Running this command in our shell, we can see that it shows us all the commits made to this git repository.

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption><p>A list of the commands made in this repository.</p></figcaption></figure>

We can escape this page by using `:qa` command and then we simply run git add \* and git revert HEAD to reverse the last commit, which according to the log above removes the flag from our file.

<figure><img src="../.gitbook/assets/Screenshot 2024-04-04 205003.png" alt=""><figcaption><p>Commands</p></figcaption></figure>

Reading the file, we now have the flag:

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption><p>Printing the file with the flag now</p></figcaption></figure>

**Flag:** picoCTF{s@n1t1z3\_cf09a485}
