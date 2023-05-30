<p align="center">
<img width="150" height="150" alt="Lovely Sim Racing" src="images/lr-logo-small.png">
</p>

<h1 align="center">Twitch Followers</h1>

<p align="center">
Workflow script for the <a href="https://j76.me/PixelClock">Ulanzi Pixel Clock</a>, based on the <a href="https://n8n.io">n8n.io</a> automation software and <a href="https://blueforcer.github.io/awtrix-light/">Awtrix Light</a>.
</p>
 
---

Display your [Twitch Followers](https://twitch.tv) on your [Ulanzi Pixel Clock](https://j76.me/PixelClock)

## Steps

#### Step 1: Upload Icon
1. Navigate to your Ulanzi Pixel Clock admin screen (usually `192.168.1.128`)
2. Select the **Icons** Tab
3. Type `20643` into the first field named **Lametric Icon ID**
4. Click **Download**

#### Step 2: Download the Twitch Followers workflow
1. Visit the [Latest Releases](https://github.com/cdemetriadis/lovely-pixelclock-n8n/releases) section and download the `Twitch_Followers.json` file to your computer

#### Step 3: Import Workflow
1. In your n8n automation server, create a new workflow
2. `Import from File` and select the downloaded Workflow

#### Step 4: Fetch Data
1. Follow the below steps to get your **Twitch API Keys**

	1. Sign in to the [**Twitch Developer Console**](https://dev.twitch.tv/console/apps) 
	2. Click **Register Your Application**
	3. Fill in the following information:
		1. **Name**: `Type a name for your app`
		2. **OAuth Redirect URLs**: `http://localhost:5678/rest/oauth2-credential/callback`
		3. **Category**: `Other`
		4. Hit **Create**
	4. Back on the Twitch Developer Console, click on **Manage**, next to your newly created app
	5. Copy your **Client ID** somewhere temporarily
	6. Click on **New Secret**
	7. Copy your **Client Secret** somewhere temporarily

2. Double-click and open the second step of the workflow, named **Fetch Data**
3. Under **Authentication**, select **Generic Credential Type**
4. Under **Generic Auth Type**, select **OAuth2 API**
5. Under **Credential for OAuth2 API**, select **Create New Credential**
6. In the pop up screen, enter the following:
	1. **Grant Type**: `Authorization Code`
	2. **Authorization URL**: `https://id.twitch.tv/oauth2/authorize`
	3. **Access Token URL**: `https://id.twitch.tv/oauth2/token`
	3. **Client ID**: `YOUR CLIENT ID`
	4. **Client Secret**: `YOUR CLIENT SECRET`
	5. **Scope**: `moderator:read:followers`
	6. **Authentication**: `Body`
	7. Hit **Connect my account**
	8. In the Twitch Pop-up window, make sure you are logged into the correct Twitch Account (if you have mutliple accounts), then click **Authorize App**
7. Back on the **Fetch Data** screen
	1. Under **Query Parameters**, replace the `XXXXX` with your `Twitch Broadcaster ID` ([Find your Twitch ID](https://www.streamweasels.com/tools/convert-twitch-username-to-user-id/))
	2. Under **Header Parameters**, Replace the `XXXXX` with your `YOUR CLIENT ID`

#### Step 5: Send to Clock
1. On the last step named **Send to Clock**, make sure the IP address in the URL field is correct (usually `192.168.1.128`)
2. On the Workflow canvas, click on the button `Execute Workflow`


## Having trouble?
Visit the [Lovely Discord](https://j76.me/LSRDiscord) and perhaps I can help you there.


## Twitter App Description
*"I want to use this API to display my Twitter Follower count on a physical device digital clock. This will be for personal use and will also be used on my Live Streams as a progress indicator. I will not show any public information related to my followers."*