# SUPERAGI toolkit
The article aims to guide you step-by-step through the process of building and adding your own custom tool with SuperAGI, a dev first opensource framework to build, manage & run autonomous AI agents. This process involves setting up a GitHub repository for your tools, installing the necessary dependencies using pip, and linking your toolkit repository to SuperAGI.

Step 1: Set Up Your GitHub Repository.

Start by creating a GitHub repository to manage your tool’s code. This will serve as your tool’s code storage and management center. Your new repository should contain the following files

📄 __init__.py: This file is crucial as it helps Python recognize your repository as a package. It’s usually an empty file.
📄 tool1.py: This is where the code for your first tool should go.
📄 tool2.py: If you have a second tool, this is where its code should reside.
📄 toolname_toolkit.py: This file will have the toolkit name, and description, followed by all tools and config details of that toolkit.
📄 requirements.txt: This file lists all the dependencies required to run smoothly.

Your repository structure should look something like this:

Your-Repository-Name
├── __init__.py
├── tool1.py
├── tool2.py
├── toolname_toolkit.py
└── requirements.txt

Step 2: Installing Necessary APIs and base tool classes via pip

Once your repository is set up, you’ll need to install the required APIs and base tool-related classes to facilitate the integration of your tool with SuperAGI.

Use the following pip command (https://pypi.org/project/superagi-tools/) Run the following command in your terminal or command prompt:

pip install superagi-tools

Step 3: Linking Your GitHub Repository to SuperAGI (locally)

Start SuperAGI using docker-compose up --build

Next, you need to add your GitHub repository link to SuperAGI’s front end.

You can either click on the “add custom tool” link at home or navigate to the toolkits section. Paste your toolkit repository and save changes. The SuperAGI tool manager will take care of the installation of your tool along with its dependencies.

The GitHub link and toolkit name are stored in a superagi/tools/tools.json like this:

{ "toolkit-name": "YOUR-GITHUB-LINK" }

Step 4: Re-build SuperAGI using Docker and start using your tools
Once the linking is completed, you have to restart your docker.

Run the following command in the terminal:

docker compose down
docker compose up --build

This command restarts your docker, builds it again, and runs it.

During the Docker run, your tool’s dependencies (specified in requirements.txt) will be installed automatically on startup by a script install-tool-dependency.sh.

Now you should be able to configure your tool settings from the toolkit section and start using them during the agent provisioning.

In case you face any challenges in building/adding your custom toolkit to SuperAGI, join our discord to work with the community to resolve the issues. We are also working on enabling the feature to list custom tools in SuperAGI cloud and SuperAGI marketplace.
