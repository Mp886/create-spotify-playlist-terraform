## Project Overview
This project utilizes Terraform to automate the creation and management of multiple Spotify playlists for various occasions, such as morning, evening, and party night.

## Prerequisites
Terraform: Ensure Terraform is installed on your machine.
Docker: Make sure Docker is installed and running.
Spotify Account: You need a Spotify account (premium access is not required).
Spotify Developer Account: Register and create an application to obtain the Client ID and Client Secret.
Spotify Provider for Terraform: Install and configure the Spotify provider for Terraform.
VS Code: Recommended for editing Terraform files.

## Steps to Complete the Project
## 1. Set Up Terraform Project
Create a new directory for your Terraform project and navigate to it in your terminal. Then, create a file named main.tf.

## 2. Define the Spotify Provider
In main.tf, define the Spotify provider:

provider "spotify" {
  api_key = "?"
}

## 3. Obtain API Key
To interact with Spotify's API, you'll need a Client ID and Client Secret.

## 4. Create a Spotify App
Go to the Spotify Developer Dashboard.
 
  -Log in with your Spotify account.

  -Click on "Create an App".

  -Fill in the required details:

Name	                                         Description
My Playlist through Terraform   |	Create multiple Spotify playlists using Terraform.

  -Redirect URI: http://localhost:27228/spotify_callback

  -Click on Settings and note down the Client ID and Client Secret.

## 5. Store Client Details
Create a file named .env to store your Spotify application's Client ID and Secret:

SPOTIFY_CLIENT_ID=<your_spotify_client_id>
SPOTIFY_CLIENT_SECRET=<your_spotify_client_secret>

## 6. Run Spotify Auth Proxy
Ensure Docker Desktop is running, then start the authorization proxy server:

docker run --rm -it -p 27228:27228 --env-file ./.env ghcr.io/conradludgate/spotify-auth-proxy
You should get an "Authorization Successful" message.

## 7. Continue with Terraform Code
Add the necessary Terraform code to create and manage your playlists.

## 8. Initialize and Apply Terraform Configuration

Initialize the Terraform configuration:

terraform init

Apply the Terraform configuration:

terraform apply

## 9. Verify Playlists on Spotify

After applying the Terraform configuration, log in to your Spotify account and verify that the playlists have been created and populated with the specified tracks.

## Conclusion

By following these steps, you can automate the creation and management of multiple Spotify playlists using Terraform. This method saves time and ensures consistency across your playlists. Customize the playlists and tracks to suit different occasions.






