<p align="center">
<img width="150" height="150" alt="Lovely Sim Racing" src="images/lr-logo-small.png">
</p>

<h1 align="center">Pitskill Stats</h1>

<p align="center">
Workflow script for the <a href="https://j76.me/PixelClock">Ulanzi Pixel Clock</a>, based on the <a href="https://n8n.io">n8n.io</a> automation software and <a href="https://blueforcer.github.io/awtrix-light/">Awtrix Light</a>.
</p>
 
---

Display your [PitSkill](https://pitskill.io) Statistsics on your [Ulanzi Pixel Clock](https://j76.me/PixelClock)

## Steps

#### Step 1: Upload Icon
1. Navigate to your Ulanzi Pixel Clock admin screen (usually `192.168.1.128`)
2. Select the **Icons** Tab
3. Type `53380` into the first field named **Lametric Icon ID**
4. Click **Download**

#### Step 2: Download the LFM workflow
1. Visit the [Latest Releases](https://github.com/cdemetriadis/lovely-pixelclock-n8n/releases) section and download the `Pitskill_Stats.json` file to your computer

#### Step 3: Import Workflow
1. In your n8n automation server, create a new workflow
2. `Import from File` and select the downloaded Workflow

#### Step 4: Fetch Data
1. Find your **Pitskill License Number** by visiting your "My Racing License" on the [Pitskill](https://pitskill.io) website. Your "License No" is located on the left, in your driver card info.
2. Double-click and open the second step of the workflow, named **Fetch Data**
3. Replace the `XXXX` in the Value field with your Pitskill License No. 

#### Step 5: Send to Clock
1. On the last step named **Send to Clock**, make sure the IP address in the URL field is correct (usually `192.168.1.128`)
2. On the Workflow canvas, click on the button `Execute Workflow`


## Having trouble?
Visit the [Lovely Discord](https://j76.me/LSRDiscord) and perhaps I can help you there.
