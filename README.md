# Blocker Bash Script

This is a simple bash script (~60 lines with the domains) designed to manage entries in your `/etc/hosts` file.

Its main goal is to help you block and unblock access to certain websites by mapping them to `127.0.0.1`.

I use it to block social media.

Works on linux and macos.

## What Does It Do?

This script:

1. **Backs up your `/etc/hosts` file** before making any changes.
2. **Adds specified domain entries** to the `/etc/hosts` file to block them when you run it with the `on` parameter.
3. **Removes those domain entries** when you run it with the `off` parameter.

## Customization

### Variables You Might Want to Change:

- **IP**: By default, it's set to `127.0.0.1`, which means it will resolve those domains to localhost. You can change it to another IP if you need to.
- **DOMAINS**: This array contains the list of domains you want to block/unblock.

```bash
IP="127.0.0.1"  # Change this if you want to map the domains to a different IP

# Add more domains as needed
DOMAINS=(
    "x.com"
    "twitter.com"
    "www.twitter.com"
    "www.x.com"
    "instagram.com"
    "www.instagram.com"
    "news.ycombinator.com"
    "layers.to"
    "www.midjourney.com"
    "nytimes.com"
    "youtube.com"
    "www.youtube.com"
    "twitch.tv"
    "www.twitch.tv"
    "www.facebook.com"
    "facebook.com"
)
```

## Usage

1. **Clone the Repository** (or just grab the script file):

   ```sh
   git clone https://github.com/DeluxrOwl/hosts-blocker.git
   cd hosts-blocker
   ```

2. **Make the Script Executable**:

   ```sh
   chmod +x hosts-blocker
   ```

3. **Run the Script**:

   - To block the specified domains:
     ```sh
     ./hosts-blocker on
     ```
   - To unblock the specified domains:
     ```sh
     ./hosts-blocker off
     ```

4. **Usage Help**:
   If you run the script without any parameters or an incorrect parameter, it will display a usage message:
   ```sh
   ./hosts-blocker
   ```

## Adding to PATH

If you want to be able to run this script from anywhere, you can add it to your PATH:

1. **Move the Script to a Directory in Your PATH**:

   ```sh
   sudo mv hosts-blocker /usr/local/bin/hosts-blocker
   ```

2. **Make Sure It's Executable**:

   ```sh
   sudo chmod +x /usr/local/bin/hosts-blocker
   ```

3. **Run the Script from Anywhere**:
   - To block:
     ```sh
     hosts-blocker on
     ```
   - To unblock:
     ```sh
     hosts-blocker off
     ```

## Important Note

This script modifies your `/etc/hosts` file, which requires sudo. You'll be prompted to enter your password when running the script (feel free to inspect the script, it's short).

---

If you encounter any issues or have suggestions, feel free to open an issue or submit a pull request.
