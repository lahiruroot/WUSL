# WUSL
WUSL Github Worshop

https://education.github.com/discount_requests/application?utm_source=15th December 2024-GITHUBWORKSHOP



# Initialize Git repository if not already initialized
if [ ! -d ".git" ]; then
  echo "Initializing a new Git repository..."
  git init
fi

# Add README.md to the staging area
git add "$FILE_NAME"
echo "$FILE_NAME added to staging area."

# Commit the changes
git commit -m "Add $FILE_NAME file"
echo "Committed changes with message: 'Add $FILE_NAME file'"

# Prompt user to set up a remote repository
read -p "Enter the remote repository URL (or press Enter to skip): " REMOTE_URL
if [ -n "$REMOTE_URL" ]; then
  git remote add origin "$REMOTE_URL"
  echo "Remote repository set to $REMOTE_URL."

  # Push to the remote repository
  git branch -M main
  git push -u origin main
  echo "Changes pushed to remote repository."
else
  echo "No remote repository URL provided. Skipping push step."
fi

exit 0
