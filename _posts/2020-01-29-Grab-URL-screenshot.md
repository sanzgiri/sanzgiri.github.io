# Grab URL Screenshot
> Grab a screenshot of web page using a "headless" chrome browser


## Setup
```
# Install chrome
sudo sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list'
sudo apt-get update
sudo apt-get install google-chrome-stable

# Find version of chrome
google-chrome --version

# Find corresponding version of chromedriver from here: https://sites.google.com/a/chromium.org/chromedriver/downloads  
# and then here:  https://chromedriver.storage.googleapis.com/index.html and download
wget https://chromedriver.storage.googleapis.com/<version>/chromedriver_linux64.zip
unzip chromedriver_linux64.zip
sudo mv chromedriver /usr/bin

# Install selenium webdriver
pip install selenium
```

```python
from selenium import webdriver  # Import selenium web driver
from IPython.display import Image

def get_screenshot(url, imagefile):

    chrome_options = webdriver.ChromeOptions()
    chrome_options.add_argument('--headless')

    driver = webdriver.Chrome('chromedriver', options=chrome_options)
    
    driver.get(url)
    res = driver.save_screenshot(imagefile)
    
    if res:
        print(f'URL screenshot for {url} saved to {imagefile}')
    else:
        print('Error getting URL screenshot')
```

```python
get_screenshot('https://phantomjs.org/screen-capture.html', 'p2.png')
Image(filename='p2.png')
```

    URL screenshot for https://phantomjs.org/screen-capture.html saved to p2.png


![png](images/2020-01-29-Grab-URL-screenshot_files/output_2_1.png)

