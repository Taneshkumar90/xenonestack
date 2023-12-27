# xenonestack

**for Round_1** -->
By saving the given file :
for example, internsctl.sh. 
Make it executable by running following command:
**"" chmod +x internsctl.sh ""**
Now, we can use the following commands:
**1: Manual Page:**
man ./internsctl.sh

**Help Option:**

./internsctl.sh --help
**Version Option:**

./internsctl.sh --version


**for more explation follow bellow given steps**

#!/bin/bash

# internsctl - Custom Linux Command for Operations
# Version: v0.1.0

# Function to display manual page
show_manual() {
  echo "internsctl - Custom Linux Command for Operations"
  echo "Version: v0.1.0"
  echo ""
  echo "DESCRIPTION:"
  echo "  internsctl is a custom command designed for specific operations."
  echo ""
  echo "USAGE:"
  echo "  internsctl [OPTIONS]"
  echo ""
  echo "OPTIONS:"
  echo "  --help    Display this help message and exit"
  echo "  --version Display the version information"
  echo "  cpu       Get CPU information"
  echo "  memory    Get memory information"
  echo "  user      User management commands"
  echo "  file      File-related commands"
}

# Function to display help
show_help() {
  echo "Usage: internsctl [OPTIONS]"
  echo ""
  echo "Options:"
  echo "  --help        Display this help message and exit"
  echo "  --version     Display version information"
  echo "  cpu           Get CPU information"
  echo "  memory        Get memory information"
  echo "  user          User management commands"
  echo "  file          File-related commands"
  # Add additional help information or examples here
}

# Parse command line arguments
case "$1" in
  --help)
    show_help
    ;;
  --version)
    echo "internsctl v0.1.0"
    ;;
  cpu)
    # Function to get CPU information
    ;;
  memory)
    # Function to get memory information
    ;;
  user)
    # User management commands
    ;;
  file)
    # File-related commands
    ;;
  *)
    echo "Error: Unknown option. Use 'internsctl --help' for usage information."
    exit 1
    ;;
esac

exit 0

**2. Help Option:**
./internsctl.sh --help
**3. Version Option:**
./internsctl.sh --version


**Section B:**

**Part 1 | Level Easy:**
#!/bin/bash

# ...

case "$1" in
  cpu)
    lscpu
    ;;
  memory)
    free
    ;;
  # ...
esac
**Part 2 | Level Intermediate:**
#!/bin/bash

# ...

case "$1" in
  user)
    case "$2" in
      create)
        # Create a new user with the given username
        useradd "$3"
        passwd "$3"
        ;;
      list)
        if [ "$3" == "--sudo-only" ]; then
          # List users with sudo permissions
          getent group sudo | cut -d: -f4
        else
          # List all regular users
          getent passwd | grep -vE "/sbin/nologin|/bin/false" | cut -d: -f1
        fi
        ;;
    esac
    ;;
  # ...
esac

**Part 3 | Advanced Level:**
#!/bin/bash

# ...

case "$1" in
  file)
    case "$2" in
      getinfo)
        file_name="$3"
        # Check if the file exists
        if [ ! -e "$file_name" ]; then
          echo "Error: File not found."
          exit 1
        fi

        # Function to get file information
        get_file_info() {
          local file_info
          file_info+="File: $file_name"
          file_info+="Access: $(ls -l "$file_name" | awk '{print $1}')"
          file_info+="Size(B): $(stat -c %s "$file_name")"
          file_info+="Owner: $(stat -c %U "$file_name")"
          file_info+="Modify: $(stat -c %y "$file_name")"

          echo "$file_info"
        }

        case "$4" in
          --size | -s)
            stat -c %s "$file_name"
            ;;
          --permissions | -p)
            ls -l "$file_name" | awk '{print $1}'
            ;;
          --owner | -o)
            stat -c %U "$file_name"
            ;;
          --last-modified | -m)
            stat -c %y "$file_name"
            ;;
          *)
            get_file_info
            ;;
        esac
        ;;
    esac
    ;;
  # ...
esac



