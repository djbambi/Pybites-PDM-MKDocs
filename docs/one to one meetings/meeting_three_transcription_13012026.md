Speaker 1 
Hi, Robin. 
Speaker 2 
Hi, David. How's it going? 
Speaker 1 
Good, thanks. Good. 
Speaker 2 
Nice, nice, nice. Yeah, thanks for the delayed message this afternoon. 
Speaker 1 
That's OK. 
Speaker 2 
First time he was sleeping in the Kita, we call it daycare, and it wasn't clear when he would wake up. Of course, he woke up exactly at 2:00 o'clock. It was kind of like, we could have called from there, but yeah. 
Speaker 1 
That's fine, it's fine. 
Speaker 2 
How's the situation, by the way? now? I mean, now you're still with your old company, so I guess you're very free, but then next. 
Speaker 1 
Yeah, there's not much. Yeah, there's not much going on. So I finish on Thursday at lunchtime. Yeah. So at the minute I've done a handover and yeah, there's not much going on. So I'm basically Python, Python, Python. 
Speaker 2 
Nice, perfect. Yeah. And I hope I gave you a good bit of a review in the middle of the weekend to give some first feedback already. I'm not sure if you saw it on GitHub. 
Speaker 1 
Yeah, I did. But I've kind of, I've done a lot more since then. 
Speaker 2 
Yeah, I saw, I saw this morning actually. 
Speaker 1 
So I've been so I've been using like the code review with CodePilot. Yeah, Coppilot yeah to review the code. And I've made some well significant changes to the way it works. So we got to go through what I what I've done and exactly. 
Speaker 2 
Yeah, that was also would be what I would suggest. So you can share your visuals to your code. And yeah, what I was like. So one thing that was important for me is that you also get. used to getting daily PR reviews, basically, ideally daily, sometimes not possible, but that's the goal at least. And that we both have the notifications set up and so on that we also quickly see when we do the reviews because it's a shame when information is not is not is missing also, right? Yeah. And so ideally you can expect that I give you feedback. Especially when you ping me, but either way on a daily basis. And if you feel like, hey, I would really like feedback here and I didn't get it yet, feel free to ping me on circle additionally. So yeah, because I mean, Copilot, like I wrote already in the PR, right, it gives some decent feedback. But also quite a lot of it is actually not so important right now. And that's of course hard for the AI to understand, right? So and it's actually, it's nice because for me also as a coach, it's always nice to see then, okay, there's a value that you have a human that guides you and of course, ignore this and focus on that. 
Speaker 1 
Yeah, 100%, 100%. So I I'm going down something else. Sorry. No worries. So yeah, add some more pitch better. Yeah, so I actually made kind of a oops. A decisions sort of document. 
Speaker 2 
Yeah, exactly. Nice. Yeah, I guess the what I know was the term ADR, for example, architectural decision record. 
Speaker 1 
Okay. 
Speaker 2 
But it's also not necessarily only architectural. So decisions marked on I think is a decent name. Yeah. 
Speaker 1 
Yeah. So yeah, it was just kind of me just sort of just well, so what I like to do is kind of explore. different ways of doing things. And then when I do settle on something, sort of try and explain why I did it and what the alternatives were. So I'm trying to do that at the minute. That's why I've gone through a few iterations. So the first one I kind of got into was the dependency injection. So. I'd read that. So for example, the requests module. So if I do dependency injection with that, it makes it easier to test the function because you just mock out the get request. Yeah. So yeah, I went down that route. And yeah, so basically created the. HTTP session outside the client and passed it in explicitly. And yeah, I'd obviously considered just creating a request session inside the function. But that's kind of, I just, I mean, obviously you can tell us, but I just, from what I've read, that's not the kind of way to do things. It's much better to do dependency injection, you know, just separation of concerns. Yes. thing, so think doing. Yeah. 
Speaker 2 
This one is actually good for that. I'm not sure if you know about this one. 
Speaker 1 
So I've got a subscription to O'Reilly for a year. Yeah. So I can go and read that. 
Speaker 2 
So you can bookmark it or like I can write you in the survey afterwards. I will give you a tear so I don't forget. It's talking exactly about this more generally. Dependency and version pattern it's called, I think, or yeah, dependency and version exactly. So hexagonal clean architecture with adapters and stuff. 
Speaker 1 
Yeah. 
Speaker 2 
It's also interesting because I'm now actually rereading the fluent Python. You may also know this one. It's very big. 
Speaker 1 
Yeah, I've got I've got that bookmarked. Yeah. 
Speaker 2 
Yeah. And it's. I like to do it also especially when like now why do we have Implemented a lot of code in the startup and then afterwards you ask yourself like, okay, what did we do right? Where did we take shortcuts and it was a good way, a good idea and where did we take shortcuts and it cost us more in the end and all this kind of things, right? So and I also like when I rewrite this the different patterns, right? Architecture patterns, design patterns and that in Python actually. You have much less that are reasonable because Python itself is already more functional and therefore you can, of course, you can try all these things. Like it's also maybe reasonable to do it at some point in PDM, right, to get used to it. So maybe implement repository pattern ones and like you now do we like ask yourself the right questions. When does it make sense? When does it not make sense? Yeah. But I also had a couple of situations where we like also with colleagues. where we went that part right and implement repository pattern. And then we never really touched the code again. And it's like a little bit the question like, was it reasonable, right? It took like a couple more developer days and then what could be done in the other side. So, yeah, I really like that you already asked yourself the question. I think here it makes sense. I didn't look into it in detail yet, but just a general pattern and also Bob Bob is watching the repo, right? So he liked it as well that you already go into this part. So, yeah, really nice. And I will make sure that in the process, right, that we focus enough on the things that are important for you, that we don't get stuck in some theoretical discussions at some point. But yeah, it's totally good. Yeah. 
Speaker 1 
What I like is just obviously this is like just a really small sort of function, you know, it's nice. You can say straight away what it does, you know. Yeah. It's nice and clean. So yeah, I like that. It's really good. Yeah. And the other thing that I looked at was what you suggested about the but using Pydantic. 
Speaker 2 
Yes. 
Speaker 1 
So I looked into that and I've done this. So basically I've created a dot end file with. 
Speaker 2 
Yep. 
Speaker 1 
The URL, the API key, the timeout. 
Speaker 2 
Yeah, now very quick question of it's already ignored, right? It seems like. 
Speaker 1 
In git. Yeah, it's in git ignore. 
Speaker 2 
Yeah, yeah, perfect. Yeah, because I see it's like slightly grayed out. That's exactly because that's a common common error, right? That you, especially now with AI, I think it's yeah, maybe. That you're accidentally committed and then the key is lost basically because it's in history. 
Speaker 1 
Yeah, 100%. Yeah, I'm very conscious of not sharing keys. I do a lot with the AWS, so. I'm constantly using kind of new keys when I'm logging in different accounts and that sort of thing. So I've got to be really conscious about sort of where they're stored and never put them in GitHub. 
Speaker 2 
Yeah. So what you can create additionally is a.env.example file and that one you can add to the git history so that. People that download the repo, they directly see, I need to set these environment variables. 
Speaker 1 
Okay, that's good. That's a good point. Yeah, that's a good point. Right. Okay, yeah, well, actually what I'm doing as well is with these recordings. I'm getting that I've found some software out and transcribe them, and then I'm getting ChatGPT summarise and creating a document. So I've got everything. So yeah, I've got everything kind of. 
Speaker 2 
Yeah, there's like lots of these small improvements that we have already thought of ourselves because even I already at some point in the last 2 years, we built a little transcription service like with the idea to create like a product out of this for agencies. We didn't finalise at the end. Maybe I think we still could and earn some money with it, but we should do this more on pirates already, right? Because it's such a low hanging fruit kind of. 
Speaker 1 
Yeah, because the beauty of doing that with Chat Chat VT, you can see you can ask it the summer, well, get the transcript, ask it to summarise it, what the key points are and what the actions are. Yeah. It's brilliant. It's just gain productivity. It just saves so much time and you can concentrate on the core of what you're trying to do. You know what I mean? So yeah, I love it. It's great. 
Speaker 2 
Perfect. Maybe it could be a little, another small app that you could build in the end that you just integrated into PDM. Anyway, just sidetracking. This looks really great. So I see all the important stuff, right? The type, a little bit of comments as well, defaults makes sense in this case, I think. Yeah, I really love Pydantic settings because like you also wrote, it's testing it while on import already. So you get very explicit errors because I mean, you can get really cryptic errors when you have an environment variable that has a wrong value and then somewhere in the code that breaks. 
Speaker 1 
Yeah, I'd heard of Pydantic, but I didn't know it could do this. That was a really good one for me, you know, so. 
Speaker 2 
OK, yeah, many people by now they know Pydentic, but they don't know about Pydentic settings yet. And then they use there are a couple of other alternatives I need to grab in my brain, but I haven't used them for 23 or 4 years now because Pydentic settings is long is available for some time now. 
Speaker 1 
Yeah, so that was that was really good. And then what I've done is I've just kind of orchestrated it with just a sorry, my I've just connected my mouse. 
Speaker 2 
I had similar issues the other day. 
Speaker 1 
It's yeah, the scroll wheels opposite to what I'm used to. So this is just purely just to kind of get it running and it and it works. I've been messing around and I've stopped it from. So that so this is what happened. So what I did was this all worked and I've broken it because. I wrote, where is it? So in the DAGs, I created the DAG wrapper and then tried to get running in Docker and came across all kinds of problems trying to get it running. And it was mainly to do with imports. So I thought I understood modules and packages and it turns out that I don't. 
Speaker 2 
Ah, okay. But I also see that this dex folder is outside the SRC. 
Speaker 1 
Yes. So I think that's possibly causing an issue. 
Speaker 2 
Yes, as well. 
Speaker 1 
Yeah. So the plan is, well, what I've been doing this afternoon is I've been just relearning about modules and packages because I didn't. Yeah, I think it's one of those things where people think they understand it, but it can cause a world of pain. 
Speaker 2 
Exactly, that's exactly actually, if you hear back the last session, that's why I advocated the source directory structure, right? Because it kind of forces you to set it up correctly and otherwise to get into paints. So I'm wondering, I'm not sure because I have looked at the dex folder and the PR. But I didn't focus so much on the directory structure, so I'm not sure if it was already in the outside the source directory or... 
Speaker 1 
Yeah, it was already, it was outside. 
Speaker 2 
Okay. So yeah, I mean that should be, is this issue fixed now or kind of? 
Speaker 1 
No, I'm working on it now. So yeah. 
Speaker 2 
We could also debug that actually because I like like and we will get more and more quick into the actual debug session and coding in the next sessions, right? But yeah. Because half an hour is anyway short, basically, but the little one. Hey, join for a coding session. 
Speaker 1 
Hello. 
Speaker 2 
So before we jump into that, I asked you last time if you want, you can think about things where you don't feel confident yet related to your work and new position. And if we want to tackle any of those or so. Otherwise, I feel like you have a really good momentum right now, developing the app, asking for questions and so on. So I think we can just go on, but I just wanted to quickly ask you, is there any major thing or so that I should maybe prepare something for or give you some direction or so or we just like we do so far? 
Speaker 1 
Not at the minute. All the other sorry, the other thing I did was I wrote some tests as well. 
Speaker 2 
Nice. Yeah. 
Speaker 1 
So I've kind of got about 4 tests there. 
Speaker 2 
Yeah. 
Speaker 1 
So yeah, and this is another thing, I should put it in the winds thing, to be honest, because I didn't fully understand how mocks worked. Yeah. And now I do. So that was that was a really good kind of moment. It was like, right, OK, now I understand. 
Speaker 2 
Yeah, I would maybe put one small asterisk there because unit test mock is also really, it kind of does everything you want it to do right in a way. And that sense is really nice, but there are also other ways of how to mock. And so I think for sure that's something I have on the radar anyway. I have like a checklist also that I like to go through at some point with the clients because normally naturally we check 50% or so anyway. And then I give options if we want to go deeper. So mock, we can go deeper. There's like Pytus monkey patch and other options. And we actually invited the creator or one of the core maintainers of Pytest to our startup to give like an in depth Pytest tutorial. And there he also gave some nice suggestions on where to go and which things are actually redundant. So because for me there was always a little bit discussion like is there still anything relevant from unit tests that could be used or should we just use Pytest? uniquely. 
Speaker 1 
Yeah. 
Speaker 2 
And it turns out that unit test, for example, unit test mock are good examples of that you can still use unit tests. 
Speaker 1 
Yes. 
Speaker 2 
But I think even I need to look into it again, it has been some time, but I think Pytest provides this unit test mock with a little bit of a wraparound that you get some extra stuff. 
Speaker 1 
So I'll take a look at that. 
Speaker 2 
Yeah, no worries. No, I mean, I think it was also a bit more of a distraction maybe right now, but could also be decent. Um, so we can for sure look deep into it in a couple of weeks or so. Yeah, but in general, yeah, Pytest is the way to go. Um, there are a couple of things from unit tests that are still useful. And anyway, Pytest uses a lot of unit test stuff under the hood. So it's just a nicer wrapper around it basically. So you get when there are errors thrown, you get a little bit more insights and so on. So yeah, the one thing that I see here which is which you didn't use yet is. Pytest mark parameterizations. 
Speaker 1 
Yes. Yeah, yeah, yeah. 
Speaker 2 
You know about that or? 
Speaker 1 
I know about parameterization. Yeah, yeah, yeah. 
Speaker 2 
And you're already comfortable using it and so on. 
Speaker 1 
I don't know. I'll again, I'll kind of I'll know when I get there and give it a try. 
Speaker 2 
Yeah, exactly because I would say it also depends a little bit what you want to test, right? So sometimes it doesn't make sense to add parameterizations. Yeah, but oftentimes you will test different. different behaviors also. And then it is really nice way to add the parameterizations. Yeah. And it also has some nice extra features and so on. So that's just something I want to make sure that you already know about. Probably you will see it in the new code base as well anyway. And the other thing is so parameterizations and fixtures. Have you already create fixtures? 
Speaker 1 
I've seen them. I haven't. Yeah, I haven't created any. 
Speaker 2 
But it's also, yeah, it's also not necessarily like you can go a long way without really needing. But then at some point, it could also be that you just notice that a couple of objects that are used for different tests I create again and again, or I import them. And if they are only relevant in the test world, then it already kind of makes really sense to create it as a fixture. 
Speaker 1 
Yeah. 
Speaker 2 
Okay, cool. So yeah, looks good. Tests, have you already debugged into the tests as well like we did last time? 
Speaker 1 
No, I didn't get that far. I've kind of, I got as far as the DAG thing. I've got this all done over the weekend and then the DAG thing. And then this is where I've kind of stopped today. So yeah. 
Speaker 2 
So we can just jump into the debugger and see what's going on with the imports. I already have an idea. And the question is how much we want to dig into it or how much we just want to fix it, like move the decks into the packages folder. 
Speaker 1 
So yeah, I kind of, I changed this because so I know these dots in front of the imports around and it doesn't work. 
Speaker 2 
It's not, you think they are wrong though. I mean, that's basically a little bit of a discussion. What we like, the last thing that I discuss also with colleagues and we read upon is that inside modules, it's fair to do relative imports. 
Speaker 1 
Yeah. 
Speaker 2 
But then of course, if you import it somewhere else, you should do the based on the package basically. So yeah, if you are in the test, then you would import, for example, from Airflow deck data pipeline and then import whatever you want. So here, the relative import is actually fine. I don't have a issue with it. 
Speaker 1 
Okay. So the reason I got hung up on it was because it was when I tried to run this in Docker, it caused the problem in Docker and it's something to do with the way I've set Docker up. So yeah, kind. 
Speaker 2 
Of. It's also, it's actually, that's exactly the reason why I like the source director, because in that case, you probably would not put the main. file or it's kind of a script actually, right? 
Speaker 1 
Yeah. 
Speaker 2 
In the script, you would not necessarily put into this package, but maybe in a scripts folder or so. 
Speaker 1 
Yeah. 
Speaker 2 
And so if you have this in the scripts folder outside of the source directory, you probably would get the same import errors as you had in the Docker file, or potentially if the installation is not correct. So we can just go go through these quickly. What is do you have the import error here in the? 
Speaker 1 
Oh no, that's something that's that's something different. I was just yeah, that was me messing around. The whole Docker thing was sorry, I need to keep reminding myself of the is it Docker? 
Speaker 2 
Docker dash compose space. There's no space between Docker and compose, I think. Theoretically, potentially, you can also write Docker space compose sometimes, but this should always work. Yeah, OK. 
Speaker 1 
Yep. 
Speaker 2 
And so you don't only see the front. OK, that's all fine. He's unpacking my pot money. 
Speaker 1 
I should text on the Xbox. 
Speaker 2 
Yeah, he's more interested in the cards than in the screen. Yeah, normally we try to avoid it, but now it seems like. 
Speaker 1 
Yeah, so that was so I had a few problems. It wasn't. It wasn't important the dad correctly, but I fixed that. But then when I try and run the down. When I try and run the dog, it just comes up with an error. So it's queued. Yeah, it's filled. Yeah, so I was a bit stuck in terms of where to find the kind of trace back. 
Speaker 2 
Yeah. 
Speaker 1 
For this. 
Speaker 2 
That's a good question. I mean, for sure in the Docker, no, and if you go to Docker desktop, do you have Docker desktop or theoretically there should always be the locks from the terminal unless Airflow, for whatever reason, doesn't give out the locks. But then. 
Speaker 1 
So is that in the container? 
Speaker 2 
Exactly. So I. Now you have Airflow scheduler and another, I think maybe in the scheduler we can look through the different ones. 
Speaker 1 
Oh, sorry. I will go. So. 
Speaker 2 
That's one way for sure. Yeah. And maybe you can maximise this a little bit and you can also search it, but you there's an error. Okay, but it's only saying that it was. 
Speaker 1 
Okay, yeah, info, info, info. Yeah, it doesn't seem to say why. 
Speaker 2 
So this is not. Yeah, so it could be because of maybe the scheduler, it doesn't really see inside what's actually running in the jobs or in the. So if you go back, then I think there's another container, it's the web server, maybe in the website, yeah, yeah, this one, how does it look like? 
Speaker 1 
That was this morning. 
Speaker 2 
At least we already saw some Python related things, right? 
Speaker 1 
Yeah, that's so that's the one that's just run 1740, 1740. 
Speaker 2 
But it could also be just fast API. So yeah, it doesn't seem to be anything. If you go further down. And you could trigger also as well again, then exactly the timestamp to see if it's because now we are not 100% sure which locks are related to setup and which ones are the back. We can also. It's interesting, but I totally agree with you that it's not 100% intuitive because I would expect somewhere here also to be logs, but it's jump into the eye. Basically, if you click on the 3 dots on the right with the links, does that give anything? And a duration time graph maybe, but. 
Speaker 1 
Yeah, let's just I mean even when I. 
Speaker 2 
Logs, there's one logs. 
Speaker 1 
Where's logs? 
Speaker 2 
Here, this is graph view and then there's gend code, audit log, logs, XCOM. Yeah, next to that on the right. 
Speaker 1 
Oh yeah, I never saw that. I was thinking I was blinded by everything. 
Speaker 2 
Yeah, no, I mean, it's a pretty hidden actually, but it's also not really. Yeah. It's not really helpful. But on the other hand. 
Speaker 1 
Oh, what's this 403 client or a forbidden for URL? 
Speaker 2 
Kind of. 
Speaker 1 
Oh, this is saying it can't read the logs. 
Speaker 2 
Yeah, have logs. Okay, fair. So maybe it's something. Do we actually have a worker? Because that was also the container that I was missing. that, I mean, in the Airflow setup, you need to have a worker, right, that actually does the work. Then you have like a scheduler that orchestrates which work to send to which workers and so on. I'm not so deep into Airflow yet, but it's a bit similar compared to prefect in that sense. So what you can check is, I think if you go to and maybe just click on the Airflow logo again. I think that brings you to the central dashboard. Dax runner runs. Can you click on browse? 
Speaker 1 
Which one? 
Speaker 2 
Browse like on the top there's a browse uprose backgrounds, tags, triggers or admin. I need to I need to also get more. What is this business class activity? Because so this could also be the issue, right? If there's no worker running to actually run the deck, then in the sense that it fails and it doesn't get any logs because there are no logs. One hypothesis right now, if you go to the cluster activity, maybe you're just clicking down. When I said when I ran it somehow jumped into my eye, but. Could also be saying life metrics in post. Thanks. Oh boy. Background types. And if you go back to the decks and click on the Hello World because the Hello World run ran, that's also a good test. Can you just trigger it again just to see if it runs now? Because that's always good, right? To have the hello world one, which should always work. If it fails as well, then it may be something completely different that is... 
Speaker 1 
Yeah, I'll run okay. 
Speaker 2 
Run ID. If you go on the run ID, does it bring you somewhere? 
Speaker 1 
Yeah, it's about this page. 
Speaker 2 
And if you go to the logs here, there are no logs actually. Interesting. Yeah. But this did run it somewhere. So can we go back to the hello world flow? Like is it triggered in the Python code? Is it triggered in the same way as the other DAG? Yeah. So here we have just a DAG from Airflow and in the weather data data. Sorry, I've covered. Yeah, classic. That's it. Same, same, I would say. Oh yeah. So yeah, I mean, that looks pretty much the same. I can try to run it also locally for me to see what's the issues. Yeah, because we have like 5 dependent minutes left, right? Yeah, it's fine. But yeah, so one thing I would already say is the decks that they are outside the source folder definitely makes it hard to import because, I mean, you can do right, you can do anything you want in Docker. But it basically means that when you move the when you install the packages inside the Docker, then it's depending on how you install it, it will either move all the files files from the package and so on in a certain directory inside the Docker. But because they insert as packages, the links to those files will be right. But then if you have the dex folder locally here in one folder, in the Docker folder, it may be in like slightly different folder, like one layer up or lower or so. 
Speaker 1 
Yeah. 
Speaker 2 
And that at least I had already some situations where I didn't want to create packages or so where this was an issue. However, you do have the test weather client, which also calls the DAG, right? If you go to that test, it runs the weather DAG or it only runs it. 
Speaker 1 
No, it's only it's only the weather client. 
Speaker 2 
Okay, yeah, because I think that could be one like the first next step would be to, I mean from my point of view, how to fix this. Move the DAX folder actually inside the source directory. 
Speaker 1 
Okay. 
Speaker 2 
And it could be, it could make sense to have a DAX, like an Airflow DAG package, what we already actually have. And it could make sense to have another package which is just weather related, right? So that all this weather domain logic and so on it lists in the one folder or this client. And maybe in some case you want to use the weather code, but in a totally different context than the Airflow decks. And so it may make sense to separate those too. For example, if you want to host it on an API, right? 
Speaker 1 
Yeah. 
Speaker 2 
And then you can create a test that calls the weather deck. So that you see if that runs and if that runs, then it means the package is properly installed, the import should work. And then if you install the package in the Docker, it should also work like this, you can have a faster iteration loop by the package. with unit tests before you go into the end to end route, because then end to end, like we just did, right, you look on the term and the UI, you look into the Docker maybe just to find out that the Python import is wrong. OK, then you can expect that easier in another way. But yeah, so maybe is this already helpful from the import perspective or? 
Speaker 1 
Yeah, definitely. I mean, I'm going to. So what I'm going to what I plan to do. Tomorrow, because I've got, I've got lots of time tomorrow. Well, I've got, I've got lots of time for the rest of the week, to be honest. So the 2 things that I want to do, I want to understand, well, 3 things really is understand the packages import thing. So I've got that fixed. That's important. Docker, understand a bit more about Docker, how it works, where to look, that sort of thing. So that shouldn't tip. too long. And also the same with Airflow as well, just kind of figure out how to get around it. And then I'll, I mean, I'll fix this. I'll fix, you know, I'll definitely fix it. I just, I need to understand in, you know, kind of how these things work. Otherwise, it's point. Otherwise, I'm just asking ChatGPT and trying things and I don't understand it, you know what I mean? So yeah. 
Speaker 2 
That sounds good. And. On that way, I think we can continue like we did so far, like a PR where you do the things all together. As we move on, the goal will be a little bit to at least temporarily create like focus pieces of work. And then in the one PR, for example, only implement the unit. If we test and unit code for the weather API, and then in the other PR, implement the deck, for example, and then in the 3rd PR, implement the Docker compose on top of that. That makes sense. Yeah, I mean, most of the times, I mean, or let's say it makes sense if you already know what you want to do and you already maybe have done it and you know how to cut it. Because in this explorative phase, it can also be good to just have one big thing and it's less overhead and so on. But it's just good then because when you go on the team, you likely have these smaller pieces of code, and then it's always good to have like smaller PRs, easy. 
Speaker 1 
To read. 100%. Yeah. This one kind of got away from me a bit. So yeah, I understand. Yeah, definitely. Alright, OK, brilliant. 
Speaker 2 
Then I guess you have. 
Speaker 1 
I've created a couple of issues as well to work on just quickly. 
Speaker 2 
Yeah, let's just quickly talk about the follow up issue part. Did you understand what I mean with that from the conversation? 
Speaker 1 
Yeah, so I'm what I got from that was for me to create issues as I go and then work on them. So I've created I created 2. So one was to add retry logic with exponential back off. It's kind of a next step thing and then extract create a helper function to build time machine. OK, I need to go back to that one because I think that was that must have been. Oh, it's called again. Copilot given suggestions and I kind of, I thought that sounds good. I'll just put that as an issue and come back to it. 
Speaker 2 
So just very quickly before we get kicked out, I guess we have 3 minutes left. Actually, I see on the top. If you go to pull requests, then there you will see that in the one review I gave. Yes. 
Speaker 1 
That's amazing. That's it now. 
Speaker 2 
Yes, maybe GitHub was. Yeah, there you go. And you can see if you go to my review, you scroll down a little bit. Yeah, if you scroll down, then you see there's a copilot popping up. Exactly. Yeah, this is what I mean. Yeah. So I think the screen sharing was a little bit delayed. So Here you can see that if you click on the three dots on the top right of my message, exactly, you can say reference in new issue. 
Speaker 1 
Okay. 
Speaker 2 
And whenever I say let's create a follow up issue on this, and this is what I mean exactly. Let's just do it once now so that you see how that looks like. Exactly. 
Speaker 1 
Okay. 
Speaker 2 
You can adapt this, of course, but for now you can just create it. 
Speaker 1 
That's cool. Yeah. All right, cool. Yeah, that's cool. 
Speaker 2 
And then the cool thing is that this is now, I mean, the title is descriptive, right? It copies over from the comment. 
Speaker 1 
Yeah. 
Speaker 2 
And if you scroll down, it also links the comment from the PR. 
Speaker 1 
All right, excellent. 
Speaker 2 
So my, I didn't actually try this one yet so much, but the idea would be that if you identify like, okay, this is just a small improvement. 
Speaker 1 
Yeah. 
Speaker 2 
Let's create a follow up issue because potentially Copilot will be able to even handle it itself because there's like very specific problem, very like there's a context around. So the chances are good that you just send it to Copilot and it creates a PR that actually looks right away very good. And this would be very cool because then you can create lots of small follow up issues and just send them to the. AI and then see if that actually makes sense. 
Speaker 1 
Okay, good. 
Speaker 2 
And like this, you keep the one PR very narrow and said, okay, in this PR, the idea was just to add this. 
Speaker 1 
Yeah. 
Speaker 2 
And all these improvement ideas, it's good for future, but I don't want to do it now. Yeah. 
Speaker 1 
And then that's good. 
Speaker 2 
Delegated to A. Yeah. 
Speaker 1 
Excellent. Yeah. Yeah. I did a blog as well. I don't know if you saw, I did a blog. 
Speaker 2 
Yeah, super cool. Yeah, really nice. I mean, you are really. pushing out a lot on the different fronts. So that's amazing, especially now that you have the time to get those started and set up. And then afterwards. 
Speaker 1 
It took a while. Yeah, MK docs. I love MK docs material. That's what this is in. So it took a little bit of time, but it was really useful. 
Speaker 2 
So yeah, nice. I think we're kicked out now any second. 
Speaker 1 
Yeah, no problem. That's great. I'll speak on Thursday then. 
Speaker 2 
Yes, see you on Thursday and write to you on PRs. 
Speaker 1 
All right, brilliant. Cheers, Robin. Thank you. 
Speaker 2 
See you you. 
Speaker 1 
Bye bye. 