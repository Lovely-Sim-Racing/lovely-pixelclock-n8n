<p align="center">
<img width="150" height="150" alt="Lovely Sim Racing" src="images/lr-logo-small.png">
</p>

<h1 align="center">Youtube Subscribers</h1>

<p align="center">
Workflow script for the <a href="https://j76.me/PixelClock">Ulanzi Pixel Clock</a>, based on the <a href="https://n8n.io">n8n.io</a> automation software and <a href="https://blueforcer.github.io/awtrix-light/">Awtrix Light</a>.
</p>
 
---

Display your [Youtube Channel Subscribers](https://youtube.com) on your [Ulanzi Pixel Clock](https://j76.me/PixelClock)

## Display
**Template:** `Subscriber Count` Rounded down to three significant figures

**Example:** `1.29K`

## Steps

#### Step 1: Upload Icon
1. Navigate to your Ulanzi Pixel Clock admin screen (usually `192.168.1.128`)
2. Select the **Icons** Tab
3. Type `5029` into the first field named **Lametric Icon ID**
4. Click **Download**

#### Step 2: Download the Youtube Subscriber workflow
1. Visit the [Latest Releases](https://github.com/cdemetriadis/lovely-pixelclock-n8n/releases) section and download the `Youtube_Subscribers.json` file to your computer

#### Step 3: Import Workflow
1. In your n8n automation server, create a new workflow
2. `Import from File` and select the downloaded Workflow

#### Step 4: Fetch Data
1. Follow the below steps to get your **Youtube API Key**

	1. Sign in to [**Google Console Cloud**](https://console.cloud.google.com) 
	2. Create a new project, name it whatever you want (sugg. "Ulanzi Clock")
	4. Go To **API'S and Services**
	5. Select your project and go to **Library**
	6. Scroll down & then Click on **YouTube Data API V3**
	7. Click on **Enable**
	9. Click on **Credentials**
	10. Click on **Create Credentials**
	11. Click on **API Key**
	12. Copy Your **YouTube API key**

2. Double-click and open the second step of the workflow, named **Fetch Data**
3. Under Query Parameters, Replace the Value `CHANNELID` with your **Channel ID** (visit your channel on Youtube, oull fin your channel ID in the URL)
4. Under Query Parameters, Replace the Value `APIKEY` with your **API Key**

#### Step 5: Send to Clock
1. On the last step named **Send to Clock**, make sure the IP address in the URL field is correct (usually `192.168.1.128`)
2. On the Workflow canvas, click on the button `Execute Workflow`

#### Step 6: Set to Active
Set the workflow to "Active", to keep it running in the background


## Having trouble?
Visit the [Lovely Discord](https://j76.me/LSRDiscord) and perhaps I can help you there.