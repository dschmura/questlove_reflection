Process

Day One: Monday, December 26th, 2016

** The start of a project has myriad decisions. The following is an attempt to document how I approach these decisions up front. After the initial project is set up, a lot of this will be captured within the commit log and README.

Recieve brief

I read the brief, then reread it, then headed into the shower. In the shower I thought through some of the flow (from a very rough, high order, 'can this path work' perspective). I also started thinking about what tools and libraries I am familiar with that might accelerate my progress towards and MVP. On my short list are using Devise for user authorization and Ransack for search. I have worked with both of these before, and couldn't think of any features that leveraging these gems would interfere with. 

** It occurred to me that I would prefer, especially with the decision to use Devise, to have postponed making it for as long as possible, and to consult with others on making a path. Authorization can be so 'sticky', meaning, the implimentation can make it difficult to extract and change course later if you're not careful. I will try to be careful.

I also started thinking of names for the app. I think the name can be important (it doesn't have to be) in helping to define the story that the app will tell. I find it helpful to spend a little bit of time trying on names. I try to concieve of clever names, often comprised of combinations of words related to the overall goal of the app. I then run the names I come up with through a brief mental story to see if the name works for the story I am trying to write. Some early contenders for this app are;

- SocRator (Socrates, questions)
- Questionable
- Inquisitor (question theme, possible Monty Python hooks)
- InquisiSort (silly, but captures the question and sorting bits.)
- QuestLove

Also spent a bit of time on http://namestormy.com

There is a whole blog to be written about name choice. I should write that someday. Anyway, I also try to find names that are actually available if possible. It isn't relevent for this project. 

Next I header to the whiteboard to start steching out the rough 'pages' that would be included in this app. I find it helpful to draft the pages out to see flow and expose opportunities to reduce steps for the user.

After I finish cleaning the whiteboard (with solvent and everything) I start to diagram a landing page, and realize I have no idea what I am doing. I re-read the brief and decide that the main focus of ths landing page should be geared towards the primary audience. In this case, think that the 'primary' audience is the individual submitting a question. This is 'primary' in this case because it is the audience that will be most impactful traffic-wise.

As I finish making this decision, the name "Questlove" pops into my head. I quick wikipedia review and I decide that this is the working title of the app. 

APP NAME: Questlove

I have decided to name the app Questlove after Ahmir Khalib Thompson, who is know professionally as such. He is 'an American percussionist, multi-instrumentalist, DJ, music journalist, record producer, and occasional actor'. His main job on The Tonight Show is to support the host (Jimmy Fallon) and the guests of the show. This role, along with the improvosational skills as a dj (remixing), both have direct annalogies for the app in this brief.  (** If this were an app headed for production, I probably would not go in this direction so we wouldn't have to rename the app later due to Trademark etc...but this is fun.)
https://en.wikipedia.org/wiki/Questlove

OTHER DECISIONS OF NOTE:

- I am using Ruby 2.4.0 and Rails 5.0.1, which were released for Christmas. I have been working in Rails 5 for a little while now, and this will give me an opportunity to become familar with the latest changes (if I brush up against them.)

- I have been playing with Twitter Bootstrap 4 alpha. I think I will use this in this project just so I can have a punt option for UI.

- Using RSpec and Postgres for my defaults. I have been using a customized template that I am developing (it is a work in progress) that I am using to codify decisions like this for me. Since there are no reasons currently to not go with these...well, that's what templates are for. 

- Most of my apps have the following pages, so they get created on rails new with my template.
  - Landing (pages#index)
  - About (pages#about)
  - Contact (pages#contact)
  - Privacy (pages#privacy)


Monday, 10:34am
```
rails new questlove
```

