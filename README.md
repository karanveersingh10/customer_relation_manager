cd ~/customer_relation_manager

cat > README.md <<'EOF'
# Customer Relationship Manager (CRM)

## Run the Application

```bash
cd ~/customer_relation_manager
bundle install
bin/rails db:migrate
bin/rails server

Main page: http://localhost:3000
Admin page: http://localhost:3000/admin

Rails Commands

bin/rails routes       # List routes
bin/rails console      # Open Rails console
bin/rails db:migrate   # Run migrations
bin/rails server       # Start application
bin/rails test         # Run tests

GitHub Repository
https://github.com/karanveersingh10/customer_relation_manager
Git Commands
git remote -v          # Show GitHub connection
git status             # Check changes
git branch             # Show current branch
git add .              # Stage changes
git status             # Review staged files
git commit -m "Update CRM project"  # Save commit
git push               # Upload to GitHub


Connect a New Repository
Use only if no remote is configured.
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git branch -M main
git push -u origin main


Replace the example URL with your actual repository URL.
Future Updates
git add .
git commit -m "Describe your changes"
git push


Security
Do not upload passwords, access tokens, config/master.key,
.env files, or private customer information.
EOF

### Upload the updated README

After the command finishes, run:

```bash
git add README.md
git commit -m "Update README commands"
git push