<p align="center">
<img width="150" height="150" alt="Lovely Sim Racing" src="images/lr-logo-small.png">
</p>

<h1 align="center">Twitter Followers</h1>

<p align="center">
Workflow script for the <a href="https://j76.me/PixelClock">Ulanzi Pixel Clock</a>, based on the <a href="https://n8n.io">n8n.io</a> automation software and <a href="https://blueforcer.github.io/awtrix-light/">Awtrix Light</a>.
</p>
 
---

Display your [Twitter Followers](https://youtube.com) on your [Ulanzi Pixel Clock](https://j76.me/PixelClock)

## Display
**Template:** `Follower Count` Rounded down to three significant figures

**Example:** `725`

## Steps

#### Step 1: Upload Icon
1. Navigate to your Ulanzi Pixel Clock admin screen (usually `192.168.1.128`)
2. Select the **Icons** Tab
3. Type `25284` into the first field named **Lametric Icon ID**
4. Click **Download**

#### Step 2: Download the Twitter Followers workflow
1. Visit the [Latest Releases](https://github.com/cdemetriadis/lovely-pixelclock-n8n/releases) section and download the `Twitter_Followers.json` file to your computer

#### Step 3: Import Workflow
1. In your n8n automation server, create a new workflow
2. `Import from File` and select the downloaded Workflow

#### Step 4: Fetch Data
1. Follow the below steps to get your **Twitter API Key**

	1. Sign in to the [**Twitter Developer Portal**](https://developer.twitter.com/en/portal/petition/essential/basic-info) 
	2. At the bottom of the page, click **Sign up for Free Account**
	3. Write up a description of your intended use of the API (you can find an example at the end of this page)
	4. Click all three check boxes and click **Submit** 
	5. Click **Create Project**
	6. Git it a Name (eg "Ulanzi Clock"), hit **Next**
	7. Select a Use Case (eg "Exploring the API"), hit **Next**
	8. Add a description (can be the same as above), hit **Next** 
	9. Type in your **App Name** (eg "Clock Display")
	10. Copy your **API Key**, **API Key Secret** & **Bearer Token**
	11. Continue by clicking **App Settings**
	12. Under **User Authentication Settings**, click **Set Up**
	13. Under **App Permissions**, select **Read** and set **Request email from users** to on.
	14. Under **Type of App**, select **Web App, Automated App or Bot**
	15. Under **App info**, enter the following:
		1. **Callback URI / Redirect URL**: `http://localhost:5678/rest/oauth1-credential/callback`
		2. **Website URL**: `https://n8n.io`
		3. **Terms of service**: `https://n8n.io`
		4. **Privacy policy**: `https://n8n.io`
	16. Hit **Save** 

2. Double-click and open the second step of the workflow, named **Fetch Data**
3. Under **Authentication**, select **Generic Credential Type**
4. Under **Generic Auth Type**, select **OAuth1 API**
5. Under **Credential for OAuth1 API**, select **Create New Credential**
6. In the pop up screen, enter the following:
	1. **Authorization URL**: `https://api.twitter.com/oauth/authorize`
	2. **Access Token URL**: `https://api.twitter.com/oauth/access_token`
	3. **Consumer Key**: `YOUR API KEY`
	4. **Consumer Secret**: `YOUR API KEY SECRET`
	5. **Request Token URL**: `https://api.twitter.com/oauth/request_token`
	6. **Signature Method**: `HMAC-SHA1`
	7. Hit **Connect my account**
	8. In the Twitter Pop-up window, make sure you are logged into the correct Twitter Account (if you have mutliple accounts), then click **Authorize App**

#### Step 5: Send to Clock
1. On the last step named **Send to Clock**, make sure the IP address in the URL field is correct (usually `192.168.1.128`)
2. On the Workflow canvas, click on the button `Execute Workflow`

#### Step 6: Set to Active
Set the workflow to "Active", to keep it running in the background


## Having trouble?
Visit the [Lovely Discord](https://j76.me/LSRDiscord) and perhaps I can help you there.


## Twitter App Description
*"I want to use this API to display my Twitter Follower count on a physical device digital clock. This will be for personal use and will also be used on my Live Streams as a progress indicator. I will not show any public information related to my followers."*