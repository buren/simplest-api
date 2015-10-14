<img class="natural-image" src="images/tb-logo.png">

```ruby
# GOTO: jacobburenstam.com/simplest-api
include LTH
author = Presenter.new(:jacob)
slides = SimplestAPI::Slides.new

wait until author.ready?

author.present(slides) do |slide|
  print slide
  any_questions? if slide.last?
end
```

---

# GOTO

## [jacobburenstam.com/simplest-api](http://jacobburenstam.com/simplest-api)

---

<div data-poller="js-poll-test">
  <p>I'm a JavaScript?</p>
  <button data-answer="JavaScript??">JavaScript??</button>
  <button data-answer="Beginner">Beginner</button>
  <button data-answer="Tinkerer">Tinkerer</button>
  <button data-answer="Coder">Coder</button>
  <button data-answer="Master">Master</button>
</div>

<div data-poller="json-poll-test">
  <p>JSON</p>
  <button data-answer="What?">What?</button>
  <button data-answer="Heard of it">Heard of it</button>
  <button data-answer="Know it">Know it</button>
</div>

<div data-poller="browser-req-poll-test">
  <p>Browser request/response model</p>
  <button data-answer="What?">What?</button>
  <button data-answer="Heard of it">Heard of it</button>
  <button data-answer="Know it">Know it</button>
</div>

<div data-poller="website-poll-test">
  <p>Have you built a website?</p>
  <button data-answer="Yes, with JS">Yes, with JS</button>
  <button data-answer="Yes">Yes</button>
  <button data-answer="No">No</button>
</div>

---

## Jacob Burenstam

__Full stack developer__

* Open source tinkerer
* Bitcoin.org translation coordinator
* Useless code enthusiast

<hr>

* [github.com/buren](https://github.com/buren)
* [keybase.io/buren](https://keybase.io/buren)

<img class="natural-image" src="images/tb-logo.png" style="max-width: 300px;"/>

---

## Full stack developer?

![Full stack developer](images/full-stack-developer.jpg)

```note
Full stack can mean pretty much whatever these days.. Basically end-to-end..
```

---

* Infrastructure (AWS, App engine, ..)
  - Scalability
  - Redundancy
  - Fail overs
  - etc..
* Database (MySQL, PostgreSQL, ..)
* Application (Ruby, Java, JavaScript, Go, ..)
* UI (HTML, CSS, JavaScript)

---

# Background

* Never programmed before
* Failed first two programming exams
  - Believe me, _really_ try not to..

  :sweat_smile:

```note
Saw my first line of code the first day of uni.

```

---
I'm a JavaScript?
<div data-poller="js-poll-test">
  <div data-chart data-refresh="5"></div>
</div>

---

JSON
<div data-poller="json-poll-test">
  <div data-chart data-refresh="5"></div>
</div>

---

Browser request/response model
<div data-poller="browser-req-poll-test">
  <div data-chart data-refresh="5"></div>
</div>

---

Have you built a website?
<div data-poller="website-poll-test">
  <div data-chart data-refresh="5"></div>
</div>

---

"JavaScript was originally developed

in <span class="highlight">10 days</span>

May 1995 by Brendan Eich.."

---

## Definite guide vs Good parts

![JavaScript - Good parts vs parts](images/js-good-vs-bad.jpg)

---

## AJAX

asynchronous JavaScript and XML

* Microsoft Outlook 1998 (obscure)
* Microsoft Outlook 2000 (~stable)
* Gmail 2004 (First large & standard compliant app)
* Google Maps 2005

---

BWT, every good Computer science idea in the last decade, has been invented at Google.

---

## JSON

JavaScript Object Notation, took over XML

---

### Its just text..

```JSON
{
  "handle": "buren",
  "age":  26,
  "languages": ["Ruby", "JavaScript", "Elixir", "Clojure", "Java"],
  "address": {
    "street": "Östervärnsgatan",
    "city": "Malmö",
    "country": "Sweden"
  }
}
```

Key-value pairs

---

## Supported data types

* Null
* Boolean
* String
* Number
* Array

Supports nested keys.

---

## Parse

```JavaScript
var jsonString = '{"handle": "buren", "favoriteLang": "Ruby", "services": {"github": true}}'
var user = JSON.parse(jsonString);
user.handle          // "buren"
user.favoriteLang    // "Ruby"
user.services.github // true
```

---

## jQuery

"jQuery is the most popular JavaScript library in use today, with installation on 65% of the top 10 million highest-trafficked sites"

* A ton of utility functions etc.
* Makes a lot of things __very__ simple
  - Most modern browsers now a days have most of these
  - You can do without jQuery if you want..

---

Remember the code from the first slide?

```ruby
include LTH

author = Presenter.new(:jacob)
slides = SimplestAPI::Slides.new

wait until author.ready?

author.present(slides) do |slide|
  print slide
  any_questions? if slide.last?
end
```

---

```ruby
DEADLINE = Time.new(2015, 10, 14, 18, 0, 0).freeze
module LTH;end
module LTH::SimplestAPI;end
String.class_eval { define_method(:last?) { false } }
NilClass.class_eval { define_method(:last?) { true } }
define_method(:wait) { puts 'Still not ready..';sleep 3 }
define_method(:any_questions?) { puts 'Any questions?' }
define_method(:feedback) { puts 'Feedback?' }
class LTH::Presenter < Struct.new(:name)
  define_method(:ready?) { Time.now >= DEADLINE }
  def present(slides); slides.to_a.each { |slide| yield(slide) };end
end
class LTH::SimplestAPI::Slides
  define_method(:initialize) { @slides = File.read('slides.md').split('---') }
  define_method(:to_a) { @slides + [nil] }
end
```

This actually makes the previous code work :trollface:

---

* [http://git.io/vnWsf](http://git.io/vnWsf)

<img src="images/github-mark.png" alt="GitHub logo" class="octocat">

---

## Thank you for listening.

---

# Questions?

<img class="natural-image" src="images/tb-logo.png"/>

---

## github.com/buren
## keybase.io/buren

<img class="natural-image" src="images/tb-logo.png" style="max-width: 300px;"/>

---

## Slides available on
### https://github.com/buren/simplest-api

<img src="images/github-mark.png" alt="GitHub logo" class="octocat">
<img class="natural-image" src="images/tb-logo.png"/>
---

<img class="natural-image" src="images/tb-logo.png"/>

<!-- Third party dependencies -->
<script src="js/libs/jquery.js"></script>
<!-- <script src="js/libs/highcharts.js"></script> -->
<script src="https://www.google.com/jsapi"></script>
<script src="js/libs/chartkick.js"></script>

<!-- JavaScript -->
<script src="js/log.js"></script>
<script src="js/resize-hack.js"></script>

<script src="js/poller.js"></script>
<script>
  PollerConfig = { url: 'https://throwawaypoll.herokuapp.com' };
</script>
