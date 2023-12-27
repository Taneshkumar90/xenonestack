# xenonestack

**for Round_1** -->

By saving the given file :

for example, internsctl.sh. 

Make it executable by running following command:

**"" chmod +x internsctl.sh ""**

Now, we can use the following commands:

**1: Manual Page:**

manual ./internsctl.sh

**Help Option:**


./internsctl.sh --help

**Version Option:**


./internsctl.sh --version




 **internsctl - Custom Linux Command for Operations**



 Commands and Options
cpu getinfo: Get CPU information.

bash

internsctl cpu getinfo
memory getinfo: Get memory information.

bash

internsctl memory getinfo
user create <username>: Create a new user.

bash

internsctl user create <username>
user list [--sudo-only]: List all regular users or users with sudo permissions.

bash

internsctl user list
internsctl user list --sudo-only
file getinfo <file-name> [--size | -s | --permissions | -p | --owner | -o | --last-modified | -m]: Get information about a file. Options to obtain specific information.

bash

internsctl file getinfo <file-name>
internsctl file getinfo --size <file-name>
Additional Information
--help: Display help message.

bash

internsctl --help
--version: Display command version.

bash

internsctl --version
Examples
Display usage examples here.
Author
Your Name
