# Release Process

## 0. Pre-releases during development

npm version 0.x.0-feat-branch.1
npm publish --tag feat-branch

## 1. Ensure everything is committed on feat/branch

git status

## 2. Switch to main branch

git checkout main

## 3. Pull latest changes

git pull origin main

## 4. Merge feat/discovery into main

git merge feat/branch

## 5. Update package.json version to 0.x.0 (remove pre-release suffix)

### You can do this manually or use:

npm version 0.x.0 --no-git-tag-version

## 6. Build the project to ensure everything compiles

pnpm build

## 7. Commit the version update

git add package.json
git commit -m "Release v0.x.0"

## 8. Create and push the version tag

git tag v0.x.0
git push origin main
git push origin v0.x.0

## 9. Publish to npm

npm publish

---

## Notes:

- Step 5: npm version updates package.json without creating a git tag (we'll do that
  manually)
- Step 6: Ensures the build works before publishing
- Step 9: Uses npm publish (not pnpm publish) which is more reliable for npm registry

### Before publishing, verify:

- You're logged into npm: npm whoami
- You have publish rights to @dodayslabs/ts-sdk
