# CI4sparkmake

A simple Bash utility to speed up development in [CodeIgniter 4](https://codeigniter.com/) by automating the creation of common file templates and instantly opening them in Visual Studio Code.

## 🚀 What It Does

This script wraps around CodeIgniter's `php spark make:` commands to:
- Create a new **controller**, **model**, **seeder**, **migration**, **filter**, **command**, **library** (will not use spark make) or **helper** (will also not use spark make)
- Automatically locate the generated file
- Open it directly in VS Code for immediate editing

This works when the code base is on a remote server and you are using an extension such as ssh-remote to work on it on your local machine. This is the only test that has been made, so I know it works. There is no reason why it wouldn't work if the code is local too (can someone please confirm that?).

## 📦 Installation

1. **Download or clone this repository**:
   ```bash
   git clone git@github.com:0RuiAlvel0/CI4sparkmake.git
   ```

2. **Make the script executable**:
   ```bash
   chmod +x spark-make
   ```

3. **(Optional) Move it to a directory in your PATH**:
   ```bash
   sudo mv spark-make /usr/local/bin/
   ```

## 🛠️ Usage

From your CodeIgniter 4 project root, run:

```bash
./spark-make [type] [Name]
```

Or, if you moved it to your PATH:

```bash
spark-make [type] [Name]
```

### Supported Types:
- `controller`
- `model`
- `seeder`
- `migration`
- `command`
- `library` <- will generate class template with placeholder method.
- `filter`
- `helper` <- helper file will have _helper appended.

### Example:
```bash
spark-make controller UserController
```
This will:
- Run `php spark make:controller User`
- Locate `app/Controllers/User.php`
- Directly open the file in VS Code after creation

or
```
spark-make helper this_is_a
```
This will:
- Create a new file inside app\Helpers with the name `this_is_a_helper.php`
- Directly open the file in VS Code after creation

## 🧠 Notes

- The script capitalizes the first letter of the filename automatically (except for helpers).
- For migrations, it searches for the timestamped file that matches the name.
- If the file is not found, it will notify you.

## 💻 Requirements

- Bash shell (Linux/macOS)
- CodeIgniter 4 installed
- Visual Studio Code, use it with the VS Code terminal
- PHP CLI

## 📄 License

MIT License. Feel free to fork, modify, and contribute!