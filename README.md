# Old-Ansimble
This project automates the deployment of a WordPress website with Docker and Ansible. The setup includes various services like Nginx, MySQL, Grafana, Prometheus, and WordPress itself.
## Prerequisites
Before you can run the playbooks, make sure you have the following installed:
- [Ansible](https://www.ansible.com/)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- [Git](https://git-scm.com/)
- [Grafana](https://grafana.com/)
## Project Structure
- `playbooks/`: Contains all the Ansible playbooks to automate the setup.
- `roles/`: Includes specific tasks for each service (e.g., MySQL, Nginx, Grafana).
- `inventory/`: The Ansible inventory file, used to define the hosts and groups.
- `vars/`: Variables for the roles and playbooks.
- `backup/`: Backup scripts for the website.
## Setting Up the Project
1. Clone the repository to your local machine:
   git clone https://github.com/galinass/old-ansimble.git
   cd old-ansimble
   2. Create a `.env` file or update the `vars` with the necessary configurations (e.g., database credentials, domain name, etc.).
## Running the Playbook
To deploy the WordPress site with all services (Nginx, MySQL, Grafana, Prometheus), run the following Ansible command:
ansible-playbook -i inventory/hosts.yml playbooks/site.yml
## Start Docker Containers
If you need to start Docker containers manually for testing or development purposes, use the following command:
docker-compose up -d
This will start all the necessary services as containers.
- ansible-playbook -i ~/old-ansimble/inventory/hosts.yml playbooks/site.yml --ask-become-pass
This command runs the Ansible playbook site.yml located in the playbooks directory, using the inventory file hosts.yml from the inventory directory. The --ask-become-pass flag prompts for the sudo password to gain elevated privileges during the execution of the play
