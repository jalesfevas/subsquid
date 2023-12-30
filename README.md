# subsquid
Install dependencies: Node.js, Docker, Git.
```bash
sudo apt-get update && sudo apt install git -y && sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
```
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
source ~/.bashrc
nvm install 18
nvm use 18
```
```bash
mkdir ~/global-node-packages
```

Config NodeJS
```bash
npm config set prefix ~/global-node-packages
```

Config Home Path
```bash
export PATH="${HOME}/global-node-packages/bin:$PATH"
```

Install Subsquid CLI
```bash
npm install --global @subsquid/cli@latest
```

Check Subsquid Version
```bash
sqd --version
```

Run The Squid
```bash
sqd init my-single-proc-squid -t https://github.com/subsquid-quests/single-chain-squid
```
```bash
cd my-single-proc-squid
```

Press Get Key button in the quest card to obtain the singleProc.key key file. Save it to the ./query-gateway/keys subfolder of the squid folder. The file will be used by the query gateway container.
```bash
sqd up
npm ci
sqd build
sqd migration:apply
```

Start Squid
```bash
sqd run .
```

Stop Squid
```bash
sqd down
```
