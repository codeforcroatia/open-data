# GitHub Action: *save-image*

Saves an image from a URL into your GitHub repo.

This allows you to cache network images to be used within your repositories. This is useful for faster loading READMEs and for URLs that timeout sometimes.

## Usage

```yml
uses: minituff/save-image@v1.4
with:
    # Required. This is the URL from which the image will be pulled
    url: 'https://cat.png'

    # Required. The relative path to where you would like the image to be stored.
    # The extension must match the URL image extention.
    # An incorrect path will result in no changes.
    imagePath: 'media/cat.png'

    # Optional. Allows for the deletion of the image if the URL fails to load
    deleteOnFail: false

    #Optional. Reject the network image if the response header content-type does not match this exactly.
    requiredContentType: 'image/svg+xml; charset=utf-8'
```

## Note

This Github action does **not** actually commit any changes. You **will** need to pair this action with a *committing* action such as [git-auto-commit-action](https://github.com/marketplace/actions/git-auto-commit).
See the example workflow below for an example.

## Example Workflow

```yml
name: Update cat pictures

on:
  schedule:
    - cron: '0 */24 * * *' # every 24 hours
  workflow_dispatch:


jobs:
  update_cat_image:
    # This is required to use the git-auto-commit-action. It must come before save-image
  - uses: actions/checkout@v2
    with:
      ref: ${{ github.head_ref }}

    # Run the save-image action
    - name: "Save cat image from URL"
    uses: minituff/save-image@v1.4
    with:
        url: 'https://cat.png'
        imagePath: 'media/cat.png'

    # If you do not commit the changes, then the action does not save to your repo
    - name: "Commit changes if necessary"
    uses: stefanzweifel/git-auto-commit-action@v4
    with:
        commit_message: Updating media/cat.png
        # The lines below disable the "co-authoring" feature of this action
        commit_user_name: github-actions[bot]
        commit_user_email: github-actions[bot]@users.noreply.github.com
        commit_author: Author <github-actions[bot]@users.noreply.github.com>
```
