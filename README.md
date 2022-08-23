# SkinAI

The basic outline of our computer vision project SkinAI is to use the image you take on the camera to find if you have any skin issues. With the image, our trained AI can determine what type of skin problem you have. It will compare your image to different images of skin problems and find out your condition with it. Then it will find out if professional medical help is necessary. This can prevent worser conditions of skin problems.

![](.README.md.upload/paste-0.2263895094401398)

<span style='font-size:xx-large'>**👁 What an MVP looks like**</span>

<span style='font-size:medium'>Our detector will track the skin of the user and identifying if your skin need medical help or not. SkinAI’s purpose in the future would be used in the medical company to quickly identify what is on the patient’s skin. It can also be used at home to find out just what is on your skin. SkinAi can identify ichthyosis, blisters, acne, rashes, and vitiligo.</span>

![](.README.md.upload/paste-0.3147693298166223)

<span style='font-size:xx-large'>**🧑🏻‍💻Tech stack**  </span>

<span style='font-size:medium'>“SkinAI” utilizes YOLOv5, an algorithm known as “You only look once”, for the purpose of detecting objects visually at unprecedented speed. It is built upon the powerful PyTorch framework that utilizes the Python programming language specifically for machine learning all through using Google Colabs as a work platform to train our model. Beyond the model, our data is augmented through the deployment of SerpApi to query limitless results from Google. Moreover, “SkinAI” is able to demonstrate a further streamlined computer vision workflow and pipeline through Roboflow. The technology will be manifested through a dynamic and interactive website designed with HTML and CSS for the frontend, and Flask as the backend web framework. </span>

![](.README.md.upload/paste-0.9092354371913163)

<span style='font-size:xx-large'>**🚧  Potential roadblocks**</span>

<span style='font-size:medium'>**\*** </span><span style='font-size:medium'>An issue that we may run into is that there are numerous types of skin diseases and it would be hard to get them all. That is why we stick to the five. We may also run into problems classifying what subset of the disease it is.</span>

<span style='font-size:medium'>However we can fix this by \-</span>

<span style='font-size:medium'>\* exposing our AI to countless images.</span>

<span style='font-size:medium'>Or</span>

<span style='font-size:medium'>\* getting the general disease right and leave the rest to the doctors.</span>

### ![](.README.md.upload/paste-0.12587936429060864)

<span style='font-size:xx-large'>**🤦🏻 Why you are making this** </span>

<span style='font-size:medium'>The purpose of this AI is to make sure our clients have healthy skin to last them through their lives. Everybody has had some sort of rash in their life but wasn't sure what it was at the time, and when you try to search it up on google it says you have a tumor. Skin\-AI let's our clients know exactly what is ailing them and prevents the situation from going further if the condition truly was dangerous. Our AI is for informing and saving people.</span>

![](.README.md.upload/paste-0.7073141051746408)

<span style='font-size:xx-large'>**🤖 Type of machine learning problem and why?** </span>

<span style='font-size:medium'>SkinAI will use a form of machine learning called Classified Machine learning. The reason for this is because we need to classified the data given to label and group the information. This allows us to identify is the image given of a person has a specific skin condition, with each one having its own grouping.  Having this AI will help us in finding and getting treatment to the people who have several certain skin problems.</span>

![](.README.md.upload/paste-0.8966851460131906)

### Quickstart Guide for Local Development

First clone this repository through 

`https://github.com/organization-x/omni`

cd into the `/app` folder

`python3 -m pip install -r requirements.txt`

edit line 29 the `main.py` file to either the URL of the cocalc server you are on or `localhost` if you are running it on your own PC

Then, clone ultralytics yolov5 in the app folder, by running 

`git clone https://github.com/ultralytics/yolov5`
`pip install -r yolov5/requirements.txt`

Run

 `python3 -m main`

to start the server on local, most changes while developing will be picked up in realtime by the server

### Quickstart Guide for Local Deployment

Make sure docker is installed on your system. Look that up if you don't know what that means.

cd into the root director of the repo then run 

`docker build -t omni .`

once built, run

`docker run -d -p 9000:80 --restart=unless-stopped --name omni omni`

you should then be able to see the `omni` container running when you run 

`docker ps -a`

if it seems to be stuck (i.e. constantly listed as `Restarting`), something is wrong with the docker image or code inside causing it to repeatedly fail.

you can start debugging the project by running 

`docker logs -f omni` 

or

`docker exec -it omni /bin/bash` for an interactive bash terminal (this option only works if the container is running and not stuck in a restart loop)

### Common Issues

`$'\r': command not found` when attempting to start docker container

this is caused by the the `entrypoint.sh` script somehow having CLRF line endings instead of LF line endings.

to fix this run

`sed -i 's/\r$//' entrypoint.sh`

### File Structure

The files/directories which you will need to edit are **bolded**

**DO NOT TOUCH OTHER FILES. THIS MAY RESULT IN YOUR PROJECT BEING UNABLE TO RUN**

- .gitignore
- config.py
- Dockerfile
- READMD.md
- entrypoint.sh
- nginx_host
- host_config
- app/
     - **main.py**
     - **best.pt** <- you will need to upload this yourself after cloning the repo when developing the site
     - **requirements.txt**
     - **utils.py**
     - templates/
          - **index.html**

### How to upload best.pt to your file structure?

Run 
`cp ../path/to/best.pt best.pt`

### best.pt ###

The weights file - must upload if you are running file on coding center or are trying to deploy.

### main.py ###

Contains the main flask app itself.

### requirements.txt ###

Contains list of packages and modules required to run the flask app. Edit only if you are using additional packages that need to be pip installed in order to run the project.

To generate a requirements.txt file you can run

`pip list --format=freeze > app/requirements.txt`

the requirements.txt file will then be updated. Keep in mind: some packages you install on one operating system may not be available on another. You will have to debug and resolve this yourself if this is the case.

### static/ ###

Contains the static images, CSS, & JS files used by the flask app for the webpage. You will need to create this and put files in it. Place all your images used for your website in static/images/ so that you can then reference them in your html files.

### utils.py ###

Contains common functions used by the flask app. Put things here that are used more than once in the flask app.

### templates/ ###

Contains the HTML pages used for the webpage. Edit these to fit your project. index.html is the demo page.

### Files used for deployment ###

`config.py`
`Dockerfile`
`entrypoint.sh`
`nginx_host`
`host_config`
**Only modify `host_config`. Do not touch the other files.**

