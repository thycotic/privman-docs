[title]: # (Run Terminal Command)
[tags]: # (macOS, standard user, policy)
[priority]: # (7)

# Run a Command in Terminal as a Different User

>**Note**: With Privilege Manager v11.1 ThycoticCentrify has added a __Run as User__ action and also modified the __Just-in-Time Group Membership__ action. Using those two actions in a policy, supersedes the following procedure.

On macOS, use the `sudo` command to run a command in Terminal as a member of a different group. Using `sudo --group` allows a non-administrative user to run a command as a member of a specific group.

By default, in macOS, the user's primary group is `staff`. Use the `id -gn` command to display the name of the current effective group:

```bash
% id -gn
staff
```

In order to configure the system so that the user account `user1` can run the `id` command as a member of the `admin` group, use the `visudo` command to create a file in the directory `/etc/sudoers.d` named `user1`. The file can have any name, but it will be convenient for it to be named for the user.

The `sudoers.d` directory is owned by `root`. You must use `sudo` to run the `visudo` command in that directory:

1. In Terminal, enter

   ```bash
   % cd /etc/sudoers.d
   % sudo visudo user1
   ```

   This opens an instance of the `vi` editor.
1. Enter the following text:

   `user1   ALL = (:admin) /usr/bin/id`

   >**Note**: You need to use a TAB character between the username `user1` and the keyword `ALL`.  
1. Press ESC to exit insert mode.
1. Type `:wq` to write the file.
1. Exit vi.

Now the user `user1` is able to run the `id` command as a member of the `admin` group:

```bash
% sudo --group admin id -gn
admin
```

Multiple commands can be listed, if separated by commas.

For more details about configuring a sudoers file, refer to the man page (`man sudoers`), or the book Sudo Mastery by Michael W. Lewis.
