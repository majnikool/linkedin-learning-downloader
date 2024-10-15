# LinkedIn Learning Video Downloader

I like to keep local copies of the courses that I watch on LinkedIn Learning.

I usually use the tool [knowbee/llvd](https://github.com/knowbee/llvd) to do this, but sometimes it fails. It's too focused on the end result, that is downloading the videos.

I'll be taking a more layered approach to automating this process. So a fail at some layer shouldn't affect the end goal. If one is able to watch the videos, then one should be able to download them no matter what. A failure in the tool shouldn't prevent this.

## Dependencies

- [requests · PyPI](https://pypi.org/project/requests/)
- [beautifulsoup4 · PyPI](https://pypi.org/project/beautifulsoup4/)

How do I find the course slug?

Click on the desired course
Your URl will look something like, https://www.linkedin.com/learning/l-essentiel-d-asp-dot-net-core-pour-dot-net-5
The course slug is: l-essentiel-d-asp-dot-net-core-pour-dot-net-5

How do I setup cookie-based authentication?

Click on the options in Google Chrome (top right with 3 vertical dots).
Click on More tools -> Developer tools
You can also reach here by using the keyboard combination: ctrl+shift+I).
Now once you’ve gained access to the developer tools, navigate to the Application tab, and copy the value of two cookies named li_at and JSESSIONID
Create a file named cookies.txt and place it in the folder you want to download your courses to
Open the cookies.txt file and paste in the values of li_at and JSESSIONID
li_at=xxxxx
JSESSIONID="ajax:xxxxxx"

```
pip install requests
```
```
pip install beautifulsoup4
```

## Layers

### 1. Download Links

Normally, one should be able to directly download the videos on LinkedIn Learning (or anywhere). However, this is not allowed for whatever (business) reasons.

Well, on the internet, nothing is unreachable. If one is able to view the video, one can also download it.

So, the first thing to do is to find these download links, and provide the user a way to download the videos.

## Output

`get-course-info.py` produces the `Info.txt` file:

![screenshot](screenshot-info.png)

`get-course-links.py` produces the `Links.html` file:

![screenshot](screenshot-links.png)

