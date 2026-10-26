
# Customer Relationship Manager (CRM)

## Customer Model
`app/models/customer.rb`

```ruby
class Customer < ApplicationRecord
  has_one_attached :image # Allows one image per customer
  validates :full_name, presence: true # Name is required
end
```

## Customers Controller
`app/controllers/customers_controller.rb`

```ruby
class CustomersController < ApplicationController
  def index
    @customers = Customer.all # Get all customers
  end

  def alphabetized
    @customers = Customer.order(:full_name) # Sort by name
  end

  def missing_email
    @customers = Customer.where(email_address: [nil, ""]) # Find missing emails
  end
end
```

## Routes
`config/routes.rb`

```ruby
root "customers#index" # Home page
get "customers/alphabetized", to: "customers#alphabetized"
get "customers/missing_email", to: "customers#missing_email"
```

## ActiveAdmin
`app/admin/customers.rb`

```ruby
ActiveAdmin.register Customer do
  # Allow these fields to be saved
  permit_params :full_name, :phone_number, :email_address, :notes, :image
end
```

## Run the Project

```bash
bundle install
bin/rails db:migrate
bin/rails server
```

## Git and GitHub Commands

```bash
git status # Check project changes
git add . # Stage files
git status # Review staged files
git commit -m "Add CRM project and README" # Save changes
git push -u origin main # Upload to GitHub
```

## Check GitHub Connection

```bash
git remote -v # Show connected repository
```

If no remote exists, create an empty repository on GitHub and connect it:

```bash
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
```
