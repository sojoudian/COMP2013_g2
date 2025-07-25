# Debian Source Configuration and APT Update

This guide explains how to switch to the root user, configure APT sources, and update the package index on a Debian system.

## Step 1: Become Root

Open a terminal and run:

```bash
su -
```

Enter the root password when prompted.

## Step 2: Backup and Update Sources List

Backup the existing APT sources:

```bash
cp /etc/apt/sources.list /etc/apt/sources.list.bak
```

Replace it with the following for **Debian 12 (Bookworm)**:

```bash
cat <<EOF > /etc/apt/sources.list
# Main Debian repositories
deb http://deb.debian.org/debian bookworm main contrib non-free non-free-firmware
deb-src http://deb.debian.org/debian bookworm main contrib non-free non-free-firmware

# Security updates
deb http://security.debian.org/debian-security bookworm-security main contrib non-free non-free-firmware
deb-src http://security.debian.org/debian-security bookworm-security main contrib non-free non-free-firmware

# Stable updates
deb http://deb.debian.org/debian bookworm-updates main contrib non-free non-free-firmware
deb-src http://deb.debian.org/debian bookworm-updates main contrib non-free non-free-firmware

# Backports
deb http://deb.debian.org/debian bookworm-backports main contrib non-free non-free-firmware
deb-src http://deb.debian.org/debian bookworm-backports main contrib non-free non-free-firmware
EOF
```

## Step 3: Update APT

Run the following command to update the package index:

```bash
apt update
```

You can now install packages using `apt install <package>`.

## Done

Your Debian system is now using the updated repository sources.
