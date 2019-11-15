# Obtaining Access to Summit

Please follow the instructions below to obtain access to OLCF's Summit Supercomputer.

## Step 1: Get an RSA token

If you were not given a temporary RSA token when you arrived, please request one now. Once you have your RSA token, please move on to Step 2.

## Step 2: Set up your RSA token

<img class="kb-img-right" src="https://www.olcf.ornl.gov/wp-content/uploads/2012/03/rsa_securid_fob.gif" alt="Image of an RSA SecudID fob" width="30%" />

### Activating a SecurID<sup>®</sup> Token

Follow the steps described below to set up your RSA SecurID Token.

> <strong>NOTE:</strong> Your username is printed on the front of the yellow envelope that your RSA token came in. It should begin with `csep`.

<ol>
 	<li>Initiate an SSH connection to home.ccs.ornl.gov using your OLCF username.
(i.e., <code>ssh userid@home.ccs.ornl.gov</code>)</li>
 	<li>When prompted for a PASSCODE, enter the 6 digits displayed on your token.</li>
 	<li>When asked if you are ready to set your PIN, answer with "y".</li>
 	<li>You will then be prompted to enter a PIN. Enter a 4- to 8-character alphanumeric PIN you can remember. You will then be prompted to re-enter your PIN.</li>
 	<li>A message will appear stating that your PIN has been accepted. Press enter to continue.</li>
 	<li>Finally, you will be prompted again with "Enter PASSCODE". This time enter both your PIN <u>and</u> the 6 digits displayed on your token before pressing enter.</li>
 	<li>Your PIN is now set and you are logged into home.ccs.ornl.gov.</li>
</ol>

### Using a SecurID<sup>®</sup> Token (fob) to Log In to Summit

> NOTE: If you are still logged in to `home.ccs.ornl.gov` from the previous section, please exit now by executing the command `exit`. To find out if you are still logged into home, you can type `hostname`. 

Initiate a connection to Summit using your OLCF username: <code>ssh userid<i></i>@summit.olcf.ornl.gov</code>

When prompted for your PASSCODE, enter your PIN followed by the 6 digits shown on your token before pressing enter. For example, if your pin is <code>1234</code> and the 6 digits on the token are <code>000987</code>, enter <code>1234000987</code> when you are prompted for a PASSCODE.

> <strong>NOTE:</strong> The 6-digit code displayed on the SecurID token can only be used once. If prompted for multiple PASSCODE entries, always allow the 6-digit code to change between entries. Re-using the 6-digit code can cause your account to be automatically disabled.

Once you have successfully logged in to Summit, you can move on to other challenges.

<hr>