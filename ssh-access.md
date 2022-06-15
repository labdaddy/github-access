##SSH keys

To use SSH, you need to put your SSH public key in your GitHub account. Your public key file is found in the ~/.ssh directory on a Mac or Linux machine and will generally be a file ending in .pub. Go to https://github.com/settings/keys

and copy/paste your public key from the public key file.

You can then clone a repository using syntax of either of the following types:

`git clone git@github.com:ACCOUNT/REPO.git`
`git clone ssh://github.com/ACCOUNT/REPO`

To confirm you are using ssh, run

`git config --get remote.origin.url`

If you see either of the following, you know you're using SSH to interact with the repository.

`git@github.com:paciorek/test-auth.git`
ssh://github.com/paciorek/test-auth

Avoiding having to enter your SSH passphrase

Note that you may be asked to enter your SSH passphrase when interacting with a repository. To avoid having to keep doing this, you can add your passphrase to your running SSH authentication agent, like this (assuming here your key is called 'id_rsa'):

`ssh-add ~/.ssh/id_rsa`

Note that you might need to start your SSH agent with:

`eval `ssh-agent -s``

More details on using the SSH agent can be found [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

If you have a repository that is using HTTPS and you want to switch to SSH, you can run either of these invocations from within a directory within your repository:

git config remote.origin.url git@github.com:ACCOUNT/REPO.git
git remote set-url origin git@github.com:ACCOUNT/REPO.git

