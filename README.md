
# 🧩 How to Use This Template

This repository is a **template** to help you create and distribute your own **Vendor Profile** for [SuperSlicer](https://github.com/supermerill/SuperSlicer) with automatic version tagging and release support.

---

### 1. Fork and Detach

- [**Fork this repository**](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)
- [**Rename your fork**](https://docs.github.com/en/repositories/creating-and-managing-repositories/renaming-a-repository)
- [**Detach it from this template**](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/detaching-a-fork) (i.e., remove the link to this original repository)

---

### 2. Define Your `VENDORID`

- Choose a unique identifier made of:
  

a-z, A-Z, 0-9, _


- Example: `MyBrand_123`
- The allowed characters are limited to ensure compatibility across scripts, filesystems, and CI tools.

---

### 3. Customize the Repository

- Edit the `description.ini` file with your profile metadata. Ensure that the `config_update_rest` is using your renamed `organisation/repository`
- In the `profiles/` folder:
- Delete all existing files.
- Add your custom files:
  ```
  profiles/
  ├── VENDORID.ini
  └── VENDORID/
      ├── bed_model.stl
      ├── icon.png
      ├── texture.png
      └── ...
  ```
- Ensure that the contents of your `profiles/VENDORID.ini` match the values of the corresponding keys defined in `description.ini`
- Rewrite this `README.md` file with your vendor-specific instructions.
- Commit and push your changes.

---

## ⚙️ GitHub Automation

This repository includes a GitHub Actions workflow that automates version tagging:

When you push to the `main` branch into github:
- It checks the combination of `config_version` and `slicer_version`.
- If a tag with this combination **does not exist**, a new tag is created.
- If the tag **already exists**, the workflow fails (to prevent duplicates).

---

## 📦 Releasing

- Once a tag is created automatically:
- Go to the **Releases** section in GitHub.
- Use the newly created tag to publish a release.
- Add release notes as needed.

> ⚠️ **Do not manually create a tag** — it's error-prone, let the script do it for you.

---

## 📚 Learn More

👉 [How to create a vendor profile (SuperSlicer Documentation)](https://github.com/supermerill/SuperSlicer/blob/master_27/doc/How%20to%20create%20a%20vendor%20profiles.md)

