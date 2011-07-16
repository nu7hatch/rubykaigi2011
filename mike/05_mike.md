<!SLIDE center main chicken>
<header style="font-size: 34px;">
  <a href="http://github.com/nu7hatch/mike">http://github.com/nu7hatch/mike</a>
</header>
<h1>
  Introducing Mike!<br />
  <small>The headless chicken</small>
</h1>

<!SLIDE center main chicken>
<header style="font-size: 34px;">
  <a href="http://github.com/nu7hatch/mike">http://github.com/nu7hatch/mike</a>
</header>
<h1>
  Introducing Mike!<br />
  <small>The headless <span style="background: #AADDFF; padding: 2px 8px;">browser</span></small>
</h1>

<!SLIDE center>
<h1 style="font-size: 55px; line-height: 85px;">
Browser with testing API in C++<br />
<small style="color: #555; font-size: 60px;">+</small><br />
Native extensions in Ruby, Python
</h1>

<!SLIDE center>
# New scaffold

<!SLIDE center bullets incremental>
* DOM parsing with LibXML2
* HTTP client powered by LibCURL
* JS processing with LibV8

<!SLIDE center meme>
<img src="images/songo.png" style="position: absolute"/>
<h1 style="position: absolute; top: 20px; left: 65px; font-size: 65px; color: #001155;">
  KAMEHAMEHAAAA!
</h1>

<!SLIDE center>
# Inspirations

<!SLIDE center bullets incremental>
* HtmlUnit framework
* WebKit browser
* Node.JS and Zombie

<!SLIDE center>
# Things done

<!SLIDE center bullets>
<ul>
  <li>Multiple Windows</li>
</ul>

<!SLIDE with-title>
# Windows

    @@@ruby
    browser = Browser.new
    page = browser.open("http://cuboxsa.com");
    page.click_link("Blog");
    
    assert_equal "http://cuboxsa.com",
                 browser.windows[0].url
    assert_equal "http://cuboxsa.com/blog",
                 browser.windows[1].url
   
<!SLIDE center bullets>
<ul>
  <li class="blur">Multiple Windows</li>
  <li>Frames support</li>
</ul>

<!SLIDE with-title>
# Frames

    @@@ruby
    page = browser.open("http://cuboxsa.com/frames.html")
    page.frames[1]
    page.frames["side"]
    ...
    
<!SLIDE center bullets>
<ul>
  <li class="blur">Multiple Windows</li>
  <li class="blur">Frames support</li>
  <li>Basic user interaction</li>
</ul>

<!SLIDE with-title>
# User interaction

    @@@ruby
    page = browser.open("http://cuboxsa.com")
    page.click_link("Contact");

    assert_equal "http://cuboxsa.com/contact.html", 
                 page.url

<!SLIDE center bullets>
<ul>
  <li class="blur">Multiple Windows</li>
  <li class="blur">Frames support</li>
  <li class="blur">Basic user interaction</li>
  <li>Basic JavaScript execution</li>
</ul>

<!SLIDE with-title>
# JavaScript

    @@@html
    <html>
    <body>
      <script>
        var foo = 1;
        foo += 10;
      </script>
    </body>
    </html>

<!SLIDE with-title>
# JavaScript
    
    @@@ruby
    assert_equal 11, page.evaluate("foo").to_i

<!SLIDE center bullets>
<ul>
  <li class="blur">Multiple Windows</li>
  <li class="blur">Frames support</li>
  <li class="blur">Basic user interaction</li>
  <li class="blur">Basic JavaScript execution</li>
  <li>Alerts/popups mocking</li>
</ul>

<!SLIDE with-title>
# Alerts

    @@@ruby
    browser.expect_alert("Hello world!")
    browser.expect_confirm("Are you sure?", true)
    browser.open("http://cuboxsa.com/alerts.html")

<!SLIDE center bullets>
<ul>
  <li class="blur">Multiple Windows</li>
  <li class="blur">Frames support</li>
  <li class="blur">Basic user interaction</li>
  <li class="blur">Basic JavaScript execution</li>
  <li class="blur">Alerts/popups mocking</li>
  <li>Neat API :)</li>
</ul>

<!SLIDE center>
# Pending stuff

<!SLIDE center bullets incremental>
* Browser compliant JavaScript layer
* JavaScript events handling
* XmlHttpRequest
* WebSockets
* Ruby extension
* ...

<!SLIDE center meme>
<img src="images/uncle.png" />
