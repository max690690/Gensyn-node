
# GENSYN INSTALLATION GUIDE BELOW

```bash
sudo apt update
```
```bash
sudo apt install -y
```

```bash
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof nano unzip iproute2
```

```bash
curl -sSL https://raw.githubusercontent.com/zunxbt/installation/main/node.sh | bash
```

```bash
screen -S gensyn
```

```bash
cd $HOME && rm -rf gensyn-testnet && git clone https://github.com/zunxbt/gensyn-testnet.git && chmod +x gensyn-testnet/gensyn.sh && ./gensyn-testnet/gensyn.sh
```

```bash
nano hivemind_exp/configs/mac/grpo-qwen-2.5-0.5b-deepseek-r1.yaml
```

```bash
cd rl-swarm
```

```bash
RL_SWARM_UNSLOTH=False ./run_rl_swarm.sh
```

```bash
[ -f backup.sh ] && rm backup.sh; curl -sSL -O https://raw.githubusercontent.com/AbhiEBA/gensyn1/main/backup.sh && chmod +x backup.sh && ./backup.sh
```

```bash
screen -ls
```

```bash
screen -r
```

> ⚠️ USE DIFFERENT AI MODEL TO CHECK THE AUTHENTICITY OF THE FILES.

## Bot : https://t.me/gensyntrackbot
## Explorer : https://gensyn-testnet.explorer.alchemy.com
## Dashboard: https://dashboard.gensyn.ai/

================================================================================================================================================================================================


If Error is:   ""bf16"  use this below cammand 


1. cd rl-swarm   (if there is rl-swarm directory is not present then only)

2. sudo apt install nano 

3. nano hivemind_exp/configs/mac/grpo-qwen-2.5-0.5b-deepseek-r1.yaml 
     access this 

4. ""bf16": false,
        "fp16": false

these two arguements should be false for cpu 

5. ctrl+o then enter to save it 

6. ctrl+x then enter to exit 

now re run your node 

python3 -m venv .venv
source .venv/bin/activate

./run_rl_swarm.sh

========================================================================================================================================================================================


**✅ Solution to the DHTNode bootstrap failed error **

If you're facing this error:

copy


RuntimeError: DHTNode bootstrap failed: none of the initial_peers responded to a ping.
You need to increase the startup_timeout value in the grpo_runner.py file.


🛠 How to Fix (Two Methods)
Method 1: Using Termius + VS Code (Recommended for GUI Users)s)**

1. Navigate to the file path:
   rl-swarm/hivemind_exp/runner/grpo_runner.py
2. Open it in VS Code (or any editor connected via Termius).
3. Fline 14747**, which should look like:

  
Python


   dht = hivemind.DHT(start=True, startup_timeout=30, **self._dht_kwargs(grpo_args))
   
4. Change startup_timeout=30 to:

  
Python


   startup_timeout=120
   
5. Save the file.Important:t:** When you return to Termius, you’ll see a popup asking to "Upload" or "Discard" the changeclick "Upload"d"** to apply your changes to the remote server.

---

 Method 2: Using Terminal + Nanono**

1. Run the command:

  
Bash


   nano rl-swarm/hivemind_exp/runner/grpo_runner.py
   
2. Find this line:

  
Python


   dht = hivemind.DHT(start=True, startup_timeout=30, **self._dht_kwargs(grpo_args))
   
3. Change 30 to 120.
4. Save changes:

   * Press Ctrl + O, then Enter to confirm.
   * Press Ctrl + X to exit.
5. Now restart your node — you're good to go!

6. ===================================================================================================================================================================================
