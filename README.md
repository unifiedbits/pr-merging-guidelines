# UnifiedBits Pull Requests & Merging Guidelines

This repository provides the best practices for creating, reviewing, and merging pull requests (PRs) across all UnifiedBits projects. Following these guidelines ensures a smooth and efficient development workflow.

---

## 🛠️ Creating a Pull Request

When creating a PR, ensure the following:

1. **Branch from `dev`**: Always create your branch from the latest `dev` branch to avoid conflicts and ensure you're working with the latest code.
   
   ```bash
   git checkout dev
   git pull origin dev
   git checkout -b feature/my-feature
   ```

2. **Descriptive Commit Messages**: Use [Conventional Commits](https://github.com/unifiedbits/commit-guidelines) for meaningful commit messages.
   
   Example:
   ```bash
   feat(auth): add login functionality
   fix(ui): resolve navbar overlap issue
   ```

3. **Pull Request Title**: The title of your PR should briefly describe the change. Follow this format:
   
   ```
   <type>(<domain>): <short-description>
   ```
   
   Example:
   ```
   feat(auth): add JWT authentication
   ```

4. **Link Related Issues**: Reference any relevant issues in your PR description.
   
   Example:
   ```markdown
   Closes #12 (for bug fix) or Resolves #5 (for feature implementation)
   ```

5. **Provide Context**: In the PR description, explain what the changes do, how they solve the problem, and any important context or steps to test.

---

## 🧑‍💻 Code Review Process

1. **Self-Review**: Before submitting, review your code for clarity, performance, and adherence to project standards.
   
2. **Request Reviewers**: Assign at least two reviewers (preferably a senior developer and a team member familiar with the affected code area).
   
3. **Be Open to Feedback**: PR reviews are collaborative. Be open to constructive feedback and be prepared to make adjustments.

4. **Tests**: Ensure that your changes are covered by tests or add new tests if necessary. PRs without proper test coverage may be rejected.

---

## 🔄 Merging the PR

Once your PR is approved, follow these steps:

1. **Merge to `dev` First**: All features and fixes should be merged into the `dev` branch. Ensure your PR is targeting `dev` (not `main`).
   
   After approval:
   ```bash
   git checkout dev
   git pull origin dev
   git merge feature/my-feature
   ```

2. **Resolve Conflicts**: If there are any merge conflicts, resolve them before merging. It's good practice to rebase your branch on the latest `dev` to ensure smooth merging.
   
   ```bash
   git rebase dev
   ```

3. **Squash Commits**: If your PR contains multiple small commits, squash them into a single meaningful commit before merging.

4. **Merge**: Once everything looks good, and all tests pass, merge the PR into `dev`. If you're using GitHub, you can squash and merge using the UI.

---

## 🚨 Special Notes

- **Avoid Merging Directly into `main`**: PRs should never be merged directly into `main`. `main` should always reflect a stable, production-ready state.
- **Hotfixes**: Only use `hotfix/` branches for urgent fixes that need to be applied directly to `main`. Ensure that any fixes are also merged into `dev`.
- **Rebasing vs Merging**: If your PR has diverged significantly from `dev`, rebase your branch before merging to avoid creating unnecessary merge commits.

---

## 📚 Resources

- [GitHub Flow](https://guides.github.com/introduction/flow/)
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
- [Squash and Merge](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-request-merging)

---

> "A great PR is like a good conversation: clear, collaborative, and constructive." – UnifiedBits

Let’s maintain a smooth and efficient development process through thoughtful PRs and merges! 🚀
