# Bigcommerce Sample App: Python
This is a small Flask application that implements the OAuth callback flow for Bigcommerce [Single Click Apps][single_click_apps]
and uses the [Bigcommerce API][api_client] to pull a list of products on a Bigcommerce store. For information on how to develop apps
for Bigcommerce stores, see our [Developer Portal][devportal].

We hope this sample gives you a good starting point for building your next killer app! What follows are steps specific
to running and installing this sample application.

### Registering the app with Bigcommerce
* Create a trial store on [Bigcommerce](https://www.bigcommerce.com/)
* Go to the [Developer Portal][devportal] and log in.
* Go to "My Apps"
* Click the button "Create an app", enter a name for the new app, and then click "Create"
* You don't have to fill out all the details for your app right away, but you do need
to provide some core details in section 4 (Technical). Note that if you are just getting
started, you can use `localhost` for your hostname, but ultimately you'll need to host your
app on the public Internet.
  * _Auth Callback URL_: `https://<app hostname>/bigcommerce/callback`
  * _Load Callback URL_: `https://<app hostname>/bigcommerce/load`
  * _Uninstall Callback URL_: `https://<app hostname>/bigcommerce/uninstall`
  * _Remove User Callback URL_: `https://<app hostname>/bigcommerce/remove-user` (if enabling your app for multiple users)
* Enable the _Products - Read Only_ scope under _OAuth scopes_, which is what this sample app needs.
* Click `Save & Close` on the top right of the dialog.
* You'll now see your app in a list in the _My Apps_ section of Develper Portal. Hover over it and click
_View Client ID_. You'll need these values in the next step.

### Getting started
* Clone this repo: `git clone git@github.com:bigcommerce/hello-world-app-python-flask.git`
* Change to the repo directory: `cd hello-world-app-python-flask`
* If you want to use virtualenv: `virtualenv ENV && source ENV/bin/activate`
* Install dependencies with pip: `pip install -r requirements.txt`
* Copy `.env-example` to `.env`
* Edit `.env`:
  * Set `BC_CLIENT_ID` and `BC_CLIENT_SECRET` to the values obtained from Developer Portal.
  * Set `APP_URL` to `https://<app hostname>`.
  * Set `SESSION_SECRET` to a long random string, such as that generated by `os.urandom(64)`.
* Run the app: `python ./app.py`

### Hosting the app
In order to install this app in a Bigcommerce store, it must be hosted on the public Internet. You can get started in development
by simply running `python app.py` to run it locally, and then use `localhost` in your URLs, but ultimately you will need to host
it somewhere to use the app anywhere other than your development system.

### Installing the app in your trial store
* Login to your trial store
* Go to the Marketplace and click _My Drafts_. Find the app you just created and click it.
* A details dialog will open. Click _Install_ and the draft app will be installed in your store.

[single_click_apps]: https://developer.bigcommerce.com/api/using-oauth-intro
[api_client]: https://pypi.python.org/pypi/bigcommerce
[devportal]: https://developer.bigcommerce.com

