# epms

Step 1: Create Individual Repositories for Each Component

    Create separate repositories on GitHub for each of your project components:
        Server
        Client
        Admin

    Initialize each component as a Git repository locally (if not already done). Navigate to each component's directory and run:

    bash

    cd documentation
    echo "# epms_documentation" >> README.md
    git init
    git add .
    git commit -m "first commit"
git branch -M main
    git remote add origin https://github.com/machinam4/epms_documentation.git
    git push -u origin main

        Repeat this process for the client and admin directories, making sure to adjust the repository URL accordingly.

Step 2: Create a Main Project Repository

    Create a main project repository on GitHub. This will act as the container for your submodules.

    Clone the main project repository locally:

    bash

    git clone https://github.com/machinam4/epms.git
    cd mainproject

Step 3: Add Each Component as a Submodule

    Add each component as a submodule to your main project:

    bash

git submodule add https://github.com/machinam4/epms_server.git server
git submodule add https://github.com/machinam4/epms_client.git client
git submodule add https://github.com/machinam4/epms_admin.git admin
git submodule add https://github.com/machinam4/epms_documentation.git documentation

Commit the additions:

bash

git add .
git commit -m "Added submodules for server, documentation"

Push the changes to the main repository:

bash

    git push origin master

Step 4: Clone the Main Project with Submodules

When someone needs to clone the project including all submodules, they can use the following commands:

    Clone the main project:

    bash

git clone --recurse-submodules https://github.com/yourusername/mainproject.git

If the repository was cloned without submodules initially, they can be fetched later with:

bash

    git submodule update --init --recursive

Step 5: Work with Submodules

    Navigate to a submodule and checkout the desired branch (if not on master):

    bash

cd server
git checkout master

Pull the latest changes in a submodule:

bash

git pull origin master

Make changes, commit, and push within a submodule:

bash

git add .
git commit -m "Updates to server"
git push origin master

    Remember that changes to submodules are tracked in the main project as well. After updating a submodule, return to your main project directory, commit the new state of the submodule, and push the changes:

    bash

        cd ..
        git add server
        git commit -m "Updated server submodule to latest version"
        git push origin master

Step 6: Update Submodules in the Main Project

When there are updates in submodules made by other team members, you'll want to update your local submodules:

bash

git submodule update --remote

This command fetches and updates for all your submodules.


