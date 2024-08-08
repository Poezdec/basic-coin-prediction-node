# Allora Worker-Chronos-Model


### Deployment - Read Carefully! 
## Step 1: 
```bash
rm -rf allora-model.sh alloraworker.sh allora-chain/ basic-coin-prediction-node/
```

## Step 2: 
```bash
apt install wget
```

## Step 3: Install Allora ( This will take time )
```bash
wget https://raw.githubusercontent.com/Poezdec/basic-coin-prediction-node/blob/main/alloraworker.sh && chmod +x alloraworker.sh && ./alloraworker.sh
```
- In the middle of the command execution, it will ask for keyring phrase, Here you need write a password (тот же что и прежде)
- During pasting `HEAD_ID` , Don't use `Ctrl+C` to copy and `Ctrl+V` to paste, instead just select the whole `KEY_ID` and Press Right Click

- Once Done Proceed to Step 4

## Step 4: Edit App.py
- Export Head-ID
```bash
cd allora-chain/basic-coin-prediction-node/
```

```bash
cat head-data/keys/identity
```

## Step 5: Edit App.py
- Register on Coingecko https://www.coingecko.com/en/developers/dashboard & Create Demo API KEY
- Copy & Replace API with your `COINGECKO API` , then save `Ctrl+X Y ENTER`.
```bash
sudo nano app.py
```


## Step 6: Edit docker-compose.yml
- Copy & Replace `HEAD-ID`  `WALLETSEEDPHRASE`
```bash
nano docker-compose.yml
```


## Step 7: Build.
```bash
docker compose build && docker compose up -d
```
------------------------------------------------------------------------------

#### Check Docker Status
```bash
docker ps
```
# Result:
<img width="1370" alt="Screenshot 1403-05-05 at 6 55 33 PM" src="https://github.com/user-attachments/assets/b58b264b-b4d7-4bb2-8ca2-2908b5d6e70c">


#### Check your node status
```bash
# Check worker logs
docker compose logs -f worker

# Check worker infernence - result 200 means- success.
docker compose logs -f inference
```
#### Check your worker logs and test the inferences using curl

```bash
# Download Checker
wget -O checkyourworker.sh https://raw.githubusercontent.com/casual1st/alloraworkersetup/main/checkyourworker.sh
chmod +x checkyourworker.sh
./checkyourworker.sh
```
allora-topic-6-worker

#### Run Checker
```bash
./checkyourworker.sh
```



