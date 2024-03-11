# zora-node

#update

sudo apt-get update && sudo apt-get upgrade -y

#Install the essential libraries.

sudo apt install curl build-essential git screen jq pkg-config libssl-dev libclang-dev ca-certificates gnupg lsb-release -y

#install Docker and Docker compose

curl -fsSL https://get.docker.com | sh && ln -s /usr/libexec/docker/cli-plugins/docker-compose /usr/local/bin

#Clone the Conduit Github repository.

git clone https://github.com/conduitxyz/node.git

cd node

#Download the Zora Mainnet Folder

./download-config.py zora-mainnet-0

#Set value of CONDUIT_NETWORK :

export CONDUIT_NETWORK=zora-mainnet-0

#Add your APIs to the environment file :

cp .env.example .env
nano .env

#Start a screen session

screen -S log

#Launch your node

docker compose up --build
