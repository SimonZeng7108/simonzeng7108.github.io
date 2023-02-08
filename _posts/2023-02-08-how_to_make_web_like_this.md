---
title: How to make a free website like this
author: simon
date: 2023-02-08 21:50:00 +0100
categories: [Web Development]
tags: [HTML, CSS, Markdown, jekyll, Web design]
math: true
mermaid: true
image:
  path: /images/2023-02-08-how_to_make_web/chirpy.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Free theme Chirpy powered by Jekyll
---
[**Jon Barron**](https://jonbarron.info/)'s [**template**](https://github.com/jonbarron/website) has become sort of gold standard portfolio for computer vision researcher's. Recently I decided to upgrade it to this site for more functionalities and of course a bit of fanciness.
Without any great knowledge about website design, I took the first step searching for some Github Page template since Github provides free host to static websites. Not only I found it's super-duper easy to do this web, but also it came to me as a treasure box with thousands of freely available gem themes. (Interestingly, jekyll is managed by RubyGems). Hence it is only right for me to share **another** tutorial as an amateur.

---
## Other great Tutorials
The Chirpy theme [**live demo**](https://chirpy.cotes.page/) gives a detailed tutorial on creating this website and posts. Another in-depth tutorial for Windows users is provided by [**Jade**](https://tech-notes.jadehawk.net/posts/Creating-This-Website/). Linux users can watch the video from [**Techno Tim**](https://docs.technotim.live/):

{% include embed/youtube.html id='F8iOU1ci19Q' %}


---
## TL;DR version
If you feel lazy and want to get the web done in 1 hour, just follow my too-long-didn't-read version below. 

## Prerequisite knowledge
- Git(not much)
- Markdown(very easy)


## Prerequisite installations
- [**Github account**](https://github.com/join)

Windows:
: 
1. Install <a href="https://git-scm.com/download/win" target="_top">Git</a>, just keep the default installation settings.<br/> 
2. Install <a href="https://rubyinstaller.org/downloads/" target="_top">Ruby+Devkit</a> latest stable release in bold text.<br/> 
3. Open a command prompt or PowerShell from Windows search bar.<br/> 
4. Install Jekyll
```powershell
gem install jekyll
``` 
5. Install bundle
```powershell
gem install bundle
```

Linux:
: 
1. Install Git<br/>
```bash
sudo apt install git-all
```
2. Install Ruby
```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
```
3. Add environment variables
```bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
4. Install jekyll and Bundler
```bash
gem install jekyll bundler
```

If installed successfully, type following commands either in Windows or Linux shell should shall the version of the packages:
```bash
ruby -v
gem -v
jekyll -v
bundler -v
```

## Build the website
Now all the required softwares should have been installed, following actions will make the minimal Chirpy theme to work. Of course there are thousands other [**themes**](https://github.com/topics/jekyll-theme) are available, the process is more or less the same.
#### 1. Fork the Chirpy starter
Make sure you fork the [**Chirpy starter**](https://github.com/cotes2020/chirpy-starter/generate), not the the [**Chirpy demo**](https://github.com/cotes2020/jekyll-theme-chirpy) repo.
name the forked repo as `GITHUB-USERNAME.github.io`. In my case, it is `simonzeng7108.github.io`.

#### 2. Clone the repo to local pc
You should clone the Github repo to your local folder either by download the repo or:
```bash
git clone https://github.com/GITHUB-USERNAME/GITHUB-USERNAME.github.io.git
```
#### 3. Customise the _config.yml
<mark>_config.yml</mark> is the main file contains the info about you such as the website tile, bio, your social links and etc... 

#### 4. Build the website locally
Open Windows or Linux shell and cd to local repo, then type
```bash
bundle
```
```bash
bundle exec jekyll s
```
Now you can check your website at `http://127.0.0.1:4000/`.

#### 5. Push to Github
For **Windows** users, one last step before pushing to Github repo, since Github cloud serve is linux based.
```bash
bundle lock --add-platform x86_64-linux
```
Then for all users, just do the regular git push commands.
```bash
git add .
```
```bash
git commit -m "Init"
```
```bash
git push
```
After successfully pushing the local repo to Github, the Github will take a few minutes to build over the cloud, you can see the process at your repo's `Actions` tab, green means build finished.

#### 6. Check your website
Ta-da, your free website is available at `https://GITHUB-USERNAME.github.io`. For more customisation or create posts, check [**Chirpy official tutorial**](https://chirpy.cotes.page/posts/write-a-new-post/)

## Common issues
<details>
<summary><strong>Posts are generated locally, but not on Github domain</strong></summary>

For some reason, Github may not recognise some changes, just go to your Github repo's 'Actions' tab, click 'Build and deploy' and click 'Run workflow' to manually run the Github build again.
</details>  