Process

# Day One: Monday, December 26th, 2016

** The start of a project has myriad decisions. The following is an attempt to document how I approach these decisions up front. After the initial project is set up, a lot of this will be captured within the commit log and README.

Receive brief

I read the brief, then reread it, then headed into the shower. In the shower I thought through some of the flow (from a very rough, high order, 'can this path work' perspective). I also started thinking about what tools and libraries I am familiar with that might accelerate my progress towards and MVP. On my short list are using Devise for user authorization and Ransack for search. I have worked with both of these before, and couldn't think of any features that leveraging these gems would interfere with. 

** It occurred to me that I would prefer, especially with the decision to use Devise, to have postponed making it for as long as possible, and to consult with others on making a path. Authorization can be so 'sticky', meaning, the implementation can make it difficult to extract and change course later if you're not careful. I will try to be careful.

I also started thinking of names for the app. I think the name can be important (it doesn't have to be) in helping to define the story that the app will tell. I find it helpful to spend a little bit of time trying on names. I try to conceive of clever names, often comprised of combinations of words related to the overall goal of the app. I then run the names I come up with through a brief mental story to see if the name works for the story I am trying to write. Some early contenders for this app are;

- SocRator (Socrates, questions)
- Questionable
- Inquisitor (question theme, possible Monty Python hooks)
- InquisiSort (silly, but captures the question and sorting bits.)
- Ask Me Another
- AskMeOnce
- QuestLove

Also spent a bit of time on http://namestormy.com

There is a whole blog to be written about name choice. I should write that someday. Anyway, I also try to find names that are actually available if possible. It isn't relevant for this project. 

Next I header to the whiteboard to start sketching out the rough 'pages' that would be included in this app. I find it helpful to draft the pages out to see flow and expose opportunities to reduce steps for the user.

After I finish cleaning the whiteboard (with solvent and everything) I start to diagram a landing page, and realize I have no idea what I am doing. I re-read the brief and decide that the main focus of the landing page should be geared towards the primary audience. In this case, think that the 'primary' audience is the individual submitting a question. This is 'primary' in this case because it is the audience that will be most impactful traffic-wise.

As I finish making this decision, the name "Questlove" pops into my head. I quick wikipedia review and I decide that this is the working title of the app. 

APP NAME: Questlove

I have decided to name the app Questlove after Ahmir Khalib Thompson, who is know professionally as such. He is 'an American percussionist, multi-instrumentalist, DJ, music journalist, record producer, and occasional actor'. His main job on The Tonight Show is to support the host (Jimmy Fallon) and the guests of the show. This role, along with the improvisational skills as a dj (remixing), both have direct analogies for the app in this brief.  (** If this were an app headed for production, I probably would not go in this direction so we wouldn't have to rename the app later due to Trademark etc...but this is fun.)
https://en.wikipedia.org/wiki/Questlove

OTHER DECISIONS OF NOTE:

- I am using Ruby 2.4.0 and Rails 5.0.1, which were released for Christmas. I have been working in Rails 5 for a little while now, and this will give me an opportunity to become familiar with the latest changes (if I brush up against them.)

- I have been playing with Twitter Bootstrap 4 alpha. I think I will use this in this project just so I can have a punt option for UI.

- Using RSpec and Postgres for my defaults. I have been using a customized template that I am developing (it is a work in progress) that I am using to codify decisions like this for me. Since there are no reasons currently to not go with these...well, that's what templates are for. 

- Most of my apps have the following pages, so they get created on rails new with my template.
  - Landing (pages#index)
  - About (pages#about)
  - Contact (pages#contact)
  - Privacy (pages#privacy)


#### Monday, 10:34am
```
rails new questlove
```

#### Monday 12:20pm

I have been doing a lot of research this morning, and charting my initial path. Part of my journey has been to try to research how other's have approached similar problems. Difficult problem to google on (by the way). I did come across the acts_as_votable gem. Might be useful, but looks a bit derelict. Spending some time gem shopping for bits that might be helpful.

#### Finish setup

I am going to finish my github/codeship setup. I like to get to continuous integration as quickly as possible. I am not going to be deploying this app to production, so I am not going to spend too much time on it, especially the capistrano bits and setting up a production environment, but having tests run when I commit code is a good thing, so I want to have that set up.

#### Search terms 

So, almost invariably, I spend some time exploring how others have approached problems similar to the one I am working on. Sometimes that can be difficult (especially defining search terms). For example;
```
  'Rails app rating questions'
  'Rails app ranking questions'
  'rails app for polling on submitted questions' **This one was pretty good
```

#### Monday, 4:30pm

Still very much in the 'noodling' phase. Thinking about how I am going to approach the problem, running scenarios through my head, avoiding actually committing to a direction. I am holding off on new coding until tomorrow at the earliest. 

Also, I am thinking about leveraging Rails 5's ActionCable for live question voting. I haven't done anything with ActionCable before, but what the hell...

# Day Two: Tuesday, December 27th, 2016

#### Tuesday, 6:45am

Woke a little late this morning. Doing some morning research and came across the 'ratyrate' gem. Going to spike an implementation of that this morning.

#### Tuesday, 10:56am

OK. So, the ratyrate gem is pretty decent for what I am trying to do. I did quick spike to poke around with it. Here are my impressions:
  - I 
  

In other news, my cold persists. I feel rather terrible if I'm honest. Only spending a small amount of time on the project today, hoping to feel better tomorrow.


# Day Three: Wednesday, December 28th, 2016

#### Wednesday, 6:05am

Went out with friends last night. Chatted about the project and, in the course of our chat, I came up with a few, possibly overly ambitious, features that would be nice to have. 

The big on is a having the presenter view include the ability to time_stamp questions so that the answer can be extracted from a recording at a later time. So, for example: 

Presenter sees a question queue that is a list of the moderated questions. When they select one to answer it pops open in a modal?? and we record the question_asked_time and when the presenter is finished and they close the question, we record the question_answered_time. These will be used in the future to create clips of the answers from an audio/video recording. These clips could then be sent to the original questioner.

We also thought it would be nice to filter questions as a user types them in to try and show similar questions that are already in the queue.

My mind keeps wandering towards rules systems. So, an anonymous attendee can submit a question but not vote on any. An authenticated attendee can vote. While the moderator can add questions to the queue, should questions automatically be added when they receive a certain number of votes? It feels like this should be dynamic (so based on volume of questions/votes somehow?). Anyway, I think I am pushing too far beyond MVP, and need to constrain myself.

#### Wednesday, 7:15pm

OK. It is clear that my ambition may be out-pacing my ability within this time frame. (If you give moose a timeline...) I am so far beyond the MVP that I am having a hard time recognizing it. This is what I am mean when I say I need to work with a team. I need the focus and redirection that others can provide. Just having someone to say 'Why are you going down that path?' who isn't me would be SO valuable right now. 

If I'm honest (and I am), I am a little nervous about the final outcome. I have chosen to forgo worrying about the end result and continue down the path of steady progress. Anxiety does no good for me at this point, and I don't have a counterpoint, so all I can do is pursue what I think this product should be, and put the pieces I can together in the time allotted. 

Oh, and it doesn't help that I came up with a way to make this a lecture capture system to boot. If I had three weeks and a team of three....

#### Thursday, 9:40pm

It was all I could do to resist scratching this whole project. I want to start over. I don't think this is my best work. I let that little devil that lures me into thinking 'this is gonna be epic' entice me down the path of scope creep, distraction and possibly my ultimate ruin. 

I am not proud of what I have done so far. 

Today was a frustrating and inept day. For example;

I went to start laying out the panel dashboard. The app is structured around panels (conference panels). Anyway, I was doing some really rough layout stuff (just creating divs with classes that had a background color and used a flex layout). The changes were not showing up on refresh. I spent 25 minutes today trying to get the changes I was applying to appear on the screen before I realized I wasn't including the stylesheet in the manifest. 

I have resolved to spend about 2-3 hours per day on this project. I would spend more, but it is the holiday, and work/life balance is important. It isn't that I am not committed to getting this job, but I really do want this to be an honest exercise. If I am going to get hired, I want it to be for the mediocre me, not some falsified veneer of a developer who builds amazing things without failing. I fail. I fail often. It is through mistakes that learn and make things that last.

So, today was like that. I poignant reminder that I have not been doing tight sprints of late, and in fact, I have been focused on developing the team and dev ops to the detriment of my programming chops. 

Hoping I can pull something together that isn't too embarrassing tomorrow. 

Oh, and I am loving this assignment. Seriously. It is challenging, and I am really struggling, but it is really great to go through this process, and observe my process as I do. I am trying really hard to be honest with my weaknesses and my strengths. I kind of wish I could do something similar every 3 - 6 months. (I know I can...but...having it assigned is actually helpful.)

My biggest complaint overall is that I am working in isolation. My biggest problem right now is that I am developing in an echo chamber. When I get stuck, I recognize that I am stuck fairly quickly, but I remain stuck because I don't have anyone to bounce ideas off of. (Kind of ironic, given that is the primary thing I want to address in a new job.)

#### Friday, 2:03pm

Following up on yesterday, I decided to try to learn and implement an ActionCable version today, but, I completely ran aground programming-wise. Things that I know are simple to do, and have done simply before, eluded me. I continued to make attempts, but nothing is working today. 

### Overall Process Reflection  

I run through a similar process for every project (or feature). In general terms 

1. Conceptualize / Initialize: Make sure I understand the problem I am trying to solve and imagine different approaches I might take towards solving them. Also, during this time I do some of the administrative work to set up the supporting environment for my work. (Setting up a project, setting up git etc...). These two things happen in parallel often.

2. Research: Based on step 1, I take a closer look at some of my possible solution approaches. This involves reading about how other people have approached similar problems, researching gems that might be useful and doing some quick 'spike' projects to test if any of my ideas from step 1 are viable. Almost everything I do at this stage gets thrown out.

Specifically in this project, I set up a test app (called upvote) so I could kick the tires on the ratyrate gem. It is a bit out of date, but there is a development branch that is further along. The setup instructions (the 'happy path') uses Devise for authorization, and since that doesn't conflict with any of the requirements for this project, that's what I will use too.

3. Feature Branches: At this point, I can start putting what I've learned into practice. I start creating feature branches to develop features or aspects of the app that I want to focus on. I find that feature branches are a good way to stay focused. (This is important, since my natural mind is constantly leaning towards entropy.)



Turbolinks load issue::
https://github.com/kossnocorp/jquery.turbolinks/issues/56


IDEAS: Do a StackOverflow type filtering on already submitted questions that might be similar to the one the user is typing. 

https://datatables.net