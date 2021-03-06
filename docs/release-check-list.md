# Pre-release

Check working tree is up to date and clean:

    rlt-updateworkbranch

Update .ts files:

    ninja -C $BDIR lupdate
    git add src/translations
    git commit -m "Update translations"

Update version:

    rlt-version --set-next $version

Update CHANGELOG.md:

    r!rlt-changelog

Tag pre-release

    rlt-tag

Commit and push

    git add .
    git commit
    git push
    git push --tags

Smoke test binary packages generated by CI

Ask translators to update their translations

# Release

Check working tree is up to date and clean:

    rlt-updateworkbranch

Update CHANGELOG.md:

    r!rlt-changelog

Bump version number in CMakeLists.txt

Commit and push

    git add .
    git commit
    git push

Smoke test binary packages generated by CI

- Test welcome text is OK
- Test screenshot matches
- Test translations are complete

Merge dev in master:

    git checkout master
    git pull
    git merge --no-ff origin/dev

Create tag:

    rlt-tag

Push:

    git push
    git push --tags

Publish generated packages on GitHub

# Spread

Write blog post
