00:21
Bye, Robin.

00:30
I cannot hear you yet. Oh, I can hear you. Can you hear me? Yes, no, I can hear you. Oh, good, good. Excellent. How's it going? Good, good. Just, yeah, just having a lot of fun, just kind of trying to sort things out  with Airflow and just get things running. So being messing around with Docker and stuff like that. So, yeah, it's been, it's been good. That sounds good.

00:59
Yeah, basically I saw your PR, right? Merge the first PR. That's great.  Also the back and forth, it will get more more natural, right? So questions, create the PR and so on. But I saw you created the second one. I just now gave the review  and um that's really important for me to do early on because uh efficient communication, right? If we invest into that right from the start, then it adds up. uh definitely. Yeah.  I think for me, it's just a case of sort of

01:28
I'm trying to get into that, like you said, that routine. Yeah. Just, you know, kind of just keep repeating it until it becomes really natural. Yeah. It's a bit odd at the minute. Yeah. But yeah, it'll come eventually. That sounds good. I will just quickly set up my camera because I'm watching my son on the camera basically sleeping all right. Now he should be good for two hours or so.

01:57
Alright, excellent. Yeah, that's my sweet spot for if I want to get done anything done.  Yeah, how old is he? Sorry? How old is he? 16 months.  Alright, okay. Yeah. You also have had kids?  Oh, yeah. So I've got uh one  is nearly 23. And the other one's 15.  So yeah, all those kind of early troubles are gone.

02:27
You're almost back to freedom. Yeah, yeah. So the oldest one, he's left. He's at university. And the other one's kind of, yeah, he's no trouble. So yeah, me and my wife are back to kind of going out on dates and things. Nice, man. Yeah, it's completely different now. yeah. Yeah, it's a bit of a different range, right? 16 months or 16 years. Oh yeah. To be honest, it re-

02:55
So think my wife suffers the most because my son is 15 and he doesn't want to know us anymore. He just wants to go out with his friends and my wife's like, Oh my God, what's happened? know? Yeah. guess as a father, as a father, you're like, Oh, I can understand you a little bit. Yeah, exactly. For the mother, it's much harder, right? Yeah. Yeah. Yeah, exactly. so yeah, it's an interesting kind of stage when they get to that age, you know? So yeah, but yeah, enjoy it. Enjoy it as much as you can. Cause. Yeah.

03:24
It flies over, you know.  Already know it's crazy basically. so yeah, he's there sleeping all tight or good. um basically, okay. Interesting. I'm not able to minimize this one window from zoom. Zoom always comes up with funny ways of  annoying, right? Like you had it the last time.

03:50
So I suggest you can share screen and  maybe just go what you've set up and how you run the Airflow Deck, how you debug it.  I'm just trying to set up another screen at the minute. m

04:17
in. uh

04:20
Yeah.  Ah, right, OK. It's the wrong way around. Sorry, just a sec.  That's it.

04:29
Right. Sorry about with me and stick.

04:38
over there.

05:01
Yeah, right. Share, share, share.

05:09
Right, I've got second screen now, so that's good.  Yeah, classic. And all these things will also get  faster and faster. Yeah. meeting that we have. In best case, of course, you have these things prepared, right? So then we jump right in. Yeah, of course. I will also see, I think I may be able to set up the meeting such that you can already join. OK. That I don't need to approve you. That would make it easier. Yeah. But Zoom also always comes up with some funky. Yeah, OK.

05:39
So,  yeah,  can you say that? Okay.  I need to just, yes, exactly. Yep.

05:48
Yeah, yeah, obviously I had everything kind of set up initially using UV.  And then what I've done is, um so I actually used, well, I was watching a Udemy  course that I've got about Airflow. So I kind of used that and a bit of Chat Sheet VT.  So I've got the  .com pose file from  Chat Sheet VT.

06:18
just as a kind of a generic airflow, that'll compose file. Then create the DAGs folder with just a very simple kind of hello world, DAG in there. And I've got that running. if I open this, oh, sorry.

06:46
Yes.

06:48
it again most

07:04
Yeah, so I've got  Airflow working on localhost.  So that's running through Docker now.  So yeah, I've got the kind of just the hello world DAG and I can just run that and it doesn't do anything really, just kind of print hello world. in the logs, can just say hello world.  And then all I did was I didn't kind of...

07:34
didn't really sort of know how to test, write a test. So all I did was I just wrote a test to test this function.  Uh, that was in the DAG.  Um, so I've just got this kind of, ah,  so,  um, I've got to admit I cheated.  got chachi VT to write this.  Um, and then I was going to kind of pull it apart and try and understand sort of what happened.  Um,  so yeah, that was,  that was it basically.  Um,

08:03
just kind of wrote the simple hello world and then just want to try and understand how best to test that.

08:12
And it's totally fine by me at least. So, um,  I would just stop the robot here. Okay. Uh, he tries to go back to the other room, but that's not close to reduce noise for the baby. Uh, so basically, um,  I agree, I think with this approach, I will need also to dig a little bit deeper because I haven't used airflow much in the past, but,  um, I think that's exactly one of the problems with airflow that you cannot easily, um, run DAGs, uh, in test environment, for example. So I think what you did.

08:42
seems reasonable. I've seen also some other approaches,  how you could do it. um At least if you want to do  not let's say unit tests or function tests, right? Because of course what we could do is create a whole end to end test where we spin up the Docker compose for example,  and then rerun tests against the Docker compose. oh That would be kind of an end to end test of the decks. So then it would actually run in airflow. The real deck would run in airflow. um

09:11
From a testing perspective, mean, you ideally you would like to do as much as possible in unit tests, right? And then maybe a little bit of other tests on top and very few end to end tests. You probably also want to have end to end tests, but you don't want to do everything in end to end tests just because. I was thinking that because I was thinking kind of, I don't want to test just the plumbing of air flow. Do you know what I mean? Cause that's just after itself. I'd rather concentrate on

09:41
So  I've done  test driven development  about three years ago. So I understand that. eh And I would rather work on unit tests  on the unit test side of things, to be honest, because I think that's more beneficial for, because airflow is just kind of one part. And I don't want to get too entrenched in sort of testing airflow. So  I'd rather concentrate on testing the Python that I write.

10:11
100%. Yeah, exactly.  um, and,  uh, it's just something that I stumbled over because I  did not use Airflow so much because I directly use Prefect because a couple of years ago, like three years ago by now, I think, or even more, I researched actually which orchestrators are there. And then I stumbled over Prefect and basically built by  engineers that have been  at Airflow before. And,  um,  so there's Prefect, can just simply run flows,  uh, locally.

10:40
And so you can very easily just run a unit, not a unit test maybe, but at least like a functional small test without setting up airflow. So  it's something, it's now interesting because I really like to go now into airflow to experience some of these pains  myself that I  haven't needed to experience so far. um And yeah, so that's, that's  exactly one point because  I mean, the beauty of  prefact and also a little bit of airflow is that you can write these decks.

11:09
pretty much in a Python file, just like a normal Python function. You just add one decorator. So it's like, hey, if you have this nicety and if you have this, that's the Pythonic way, then it would be amazing if you can also just test it that way, but unfortunately not for Airflow. So yeah, long story short, I agree with you. Like I guess in many cases it makes sense anyway to architect the code in a way that in the decks, it's just a very small wrapper around the Python function for example.

11:38
And then the Python function you can test completely without Airflow.  And the DAG itself you don't need to test because you trust Airflow to kind of  know what they're doing.  However, like my experience with Prefect was that you do have stuff that breaks.  the function itself may work,  but then somehow  maybe you give a big data frame or so as an input.

12:07
And then somehow that breaks airflow. um And for these kind of things, it could be nice to have  not necessarily end-to-end tests, but at least  have airflow in between. Because then  there's a higher chance that you would catch these kind of  edge cases, maybe, or whatsoever. um But I would say for our purpose now, for sure, let's keep it very simple, step by step, and so on. And maybe later we come back to this and then try to set it up in a nicer way. em

12:34
Yeah, if we, if we leave it all kind of later on then, so I start  the new job on the 19th of January. Yeah. So I'll kind of start to understand how they use Airflow. Yeah.  Basically in a couple of weeks time, I'll have a better understanding. I should have a better understanding of kind of where I want to go with Airflow. Yeah. Yeah. So yeah, definitely. I'm more interested now in kind of the more of ETL. Yeah. End to end pipeline.

13:04
So the orchestration is kind of going to be the final bit.  Yeah. So yeah, that's also why in the PR that I just reviewed, I also made a couple of comments where I said, hey, let's create a follow up issue for this. So  Co-pilot made some valid claims that, this is not good for production setup. Yeah, we agree, but that also was not the goal right now. Right. uh That's all also anyway, good questions, right? Some of these questions, maybe once you look into their code base, you directly see one way of how to do it.

13:33
And it's fine. And then you don't need to dig deeper into it. You can just do it for your project as well.  And some other questions, maybe very valid questions, that would be good that we clarify them as early as possible so that you know a new job, you directly hit the ground running and  they get the feeling like, oh man, this guy is already deep into stuff.  That's the goal, guess, right? Yeah, that's what I want.  Yeah, exactly. So  that's also why I think  we focus on what's most impactful for you to start good at the 19th.

14:00
And then while you're starting, make sure that you um hit the ground running and answer the big important questions quickly. Cool. Just in terms of,  just quickly in terms of like the project. I haven't really got, well, I've been looking at quite a few data sources um and I haven't really landed on anything that jumps out at the minute.  kind  of uh

14:28
Well, I was going to ask you sort of what you might suggest.  Good. Because what I'm thinking is I want something that isn't just a toy sort of data set. It's more kind of maybe it's going to update every day. Yeah. You know, give us, you know,  a substantial amount of data so we can do a lot of PySpark stuff. Yeah. Yeah. So something that we could do  is also a little  bit close to what I'm interested in, but

14:54
uh So energy and weather in general, meteorology. mean, that's also something that you like, right?  So that's maybe something where also you are already comfortable with the format. So it's like something that is a nice start. So we could do something where we fetch weather data on a daily basis or so. And then maybe  do some stuff with the weather data. We could run our own simple analysis or our own simple  processing. And then we could add.

15:22
also further uh data from energy uh markets or from system or so. That'd be good. Yeah. There are some nice APIs and other formats,  open source or open data basically. Yeah. So those are nice because it's not too tough for access.  Something, for example, at uh Flexa also we use  an API to get the prices for tomorrow. Yeah. So you could download a weather forecast from some public source.

15:51
You could download the prices and you maybe could make a simple em analysis of how much they are correlated or so.  And then you could do  second analysis of now actual prices from the past or so and actual data from the past and then do some stuff on that. Yeah. Yeah.  So I was thinking possibly maybe some kind of Streamlit dashboard. Yeah. I'm a fan of Streamlit. Yeah. I like Streamlit. Yeah. It's good.  I think in the decision app, right? We also use Streamlit.

16:21
I'm not if you it yet. Yeah. So em that's actually in the decision app series. We start with a stream that prototype. Oh, that's right. Yeah. I watched the first one. Yeah. Yeah, exactly. So because I think it's nice for if you have an idea and you just want to get it out quickly. Yeah. Yeah. And then as soon as you notice like, okay, my now stream that is behaving a bit buggy, it's getting slower and slower because you try to use that state for as a backend, but yeah, it's maybe not the best way to use it.

16:48
then it's  maybe reasonable to put a fast API backend as a backend. And the stream that only calls the endpoints.  And like this, can basically detach it. And then afterwards, it could say, hey, now I want to have a really beautiful  frontend.  Streamlet is nice and fast, but it is also limited in how you can  adapt it, basically.  So then you can put a JavaScript frontend, for example, on top of the  fast API backend. And so you have this.

17:17
kind of smooth transition from simple stream of prototype, which goes really fast to sophisticated web app basically. good. Yeah. And I've got, I've got another idea for something I want to do. So it's a, it's a bit of an odd one really. So I live in that. So I live in a place called Sunderland. It's in the Northeast of England. Yeah. And so we've, we've got a football team.

17:43
Ah, yeah. They're in the Premier League at the minute and they're doing quite well. And the stadium is called the Stadium of Light. Now, at the Stadium of Light, they've got a thing called the Wall of Fame. So about 10 years ago, maybe, um you could purchase a brick and you could make an inscription in the brick. Yeah.

18:10
and then they put these bricks in panels on the side of this  on the outside of the stadium. So all around the stadium, you've got all these panels with people's bricks is about twenty five thousand bricks.  Yeah. Well,  so um and each one's in a panel and the panel is designated with like seven or whatever, because it's  panel seven in the South Stand. Now, there's no that  there's no kind of public way  of finding bricks.

18:41
So people have got to contact the club to find them. So what I wanted to do was basically take a photograph of each panel and then em for a few of the panels,  I'm gonna make CSV files  with each brick, its location,  what the text says,  that sort of thing,  And  then create em some

19:11
a web, well,  a pipeline to ingest these CSVs into a database and then create some kind of front end where there'll be a map of the stadium with each panel location.  And  you can kind of, you can click on each panel to see the image or do a search for an inscription on a brick and actually find the location where it is.  so 25,000 bricks is a lot of work to  turn into CSV files.

19:41
So what I was thinking was, because there's a message board where a lot of people who are Sunlin fans go. And what I could do is open that up to people where they could transcribe a panel for me by some kind of method on the front end. And then they own that, they get sort of a nice little kind of this person, know, basically took the data from the panel.

20:10
and created it for this website. So then it kind of crowdsources.  That's pretty cool, actually.  I was just thinking that  with this state where AI is now at, I think it could even be that  if you make a photo, maybe you say you request people to make a photo with geo location. And then you could basically say  people can upload the photo and then the AI extracts automatically like the  things from the bricks basically.

20:39
And maybe  you could have like a  simple surface or interface where people can just say it's correct or they can make some edits, right? If the recognition was not good. Like this is  something that you could yourself already use, right? To make it much more smooth.  And  it could also be something that people literally  do themselves. If they feel like, hey,  this brick isn't there yet. Okay. Then uh you can make a photo and upload it and it's there.

21:08
kind of, yeah. Maybe we can. Yeah, so I thinking, I'm going to do that regardless, like in the, you because I think it's a really good sort of community archive thing. Yeah. I mean, I'd probably just have to contact the club. Yeah. Just to make sure that they're happy with it. But I want to do it anyway, even if it's just for me. Exactly. Yeah, exactly. You can do it anyway. And then when it works, you can ask them like, hey, I built this little thing. Would you be interested in? Yeah. Yeah. That's cool. Yeah. That's super cool.

21:37
Yeah, so I would say that's second app idea, right? So  more of a toy example, maybe something that we can already start doing a little bit,  but priority on the production level data pipeline.  And then  potentially in the last weeks or so we can get it started. Because I think  the way I think right now about it of a prototype with Streamlit could be a matter of a couple of hours, pack something together to see if  it quickly works.

22:06
And then um oftentimes with AI is like you get to 80 % solution pretty fast, but then it's hard to get to 100%.  But whenever you have this situation of, for example, exactly this use case, upload a photo, AI tries to extract what is in there. You have a field where the user can actually edit it.  And then case the AI doesn't need to be perfect. And it's still quite a lot of help because

22:33
If you have to type everything, takes like hours and hours. But if you just need to make some fixes and it's reasonably good in the beginning, then it's maybe good enough.  Yeah, super cool. em Yeah, okay. So maybe jumping back to current session. em I wanted to quickly jump into the debugger nonetheless. to especially focus now on the debugging iteration speed. em

23:00
And I see your screen again. So maybe you can just show how you would run the test.

23:08
Oh, um, so...

23:13
Ah,  yeah, so usually I just do  UV run  test.

23:29
Okay. Yeah. And that works, right? That's  the way, if you want to run everything makes sense. Now the other way, how you can  use it in cursor and VS code because um so cursor is another editor focusing on AI, right? I have used only VS code so far, like the last couple of weeks, I started using cursor a bit because I heard people really like it. And  as I come back to coding, it's maybe a way, a good point in time to try out. Anyway, um it's also VS code, right? So cursor is built on top of VS code.

23:59
It's almost the same  visual experience. So  you can see on the left side, there's this chemistry glass, which is basically the extension for testing.

24:15
So which one? On the left side in the extension panel.  Oh, yes. Which one is it? Right there  above. That one. Oh, okay. Yeah. So here you can click on configure Python tests. Okay. I've never used this part before. Then, you can select PyTest.

24:38
Yeah, below exactly and you can hit enter. Oh, this one paytest.

24:46
I'm just checking if my son wakes up. I just said, actually, he slept, fall asleep and 120 around. So now he's back into light sleep. Maybe I need to talk less loud. Yeah, you can select the test directory.

25:06
And now you can see how the tests were explored exactly. And you can hit this button on the top to run all tests. Ah, okay. Oh wow, didn't realize that. Yeah, this is amazing because this is the way I develop it. When I do TDD, I create the tests, right? And then afterwards I debug the single tests and I show how you can do that in a minute. So you can...

25:34
Click on the left of the 12, for example, in the editor. So on the left of line 12, and then there will be a red dot.  Click. And then  on the left side, you can hover over the test, DAG imports. And now on the right, you see one play button with a bug. So that's for debugging. In the middle, yep.

25:58
So now it starts the debugger, but with this test as an entry point. And what this means is that below you have the debug console and in the debug console, can now explore the variables that are currently available. The execution stopped at line 12 at your break point, the break point that you set. So if you would type for example, DAG back in the debug console below. And you get auto completion as well.

26:30
Enter.

26:33
Yeah, you see that now you get  this object and you can explore  it.  That's amazing.  Exactly. That's why like the second session, I always like to do this because this completely opens up a new world for  you to explore stuff, right? Why does things break and so on? Because exactly em you may now have the airflow deck that breaks for some reason. Yeah. And you want to go inside and see how do objects look like. em

27:02
Are they looking like I expect them or maybe there's something off basically the DAX folder, for example, right? The classic, you did it correctly. I would do it similar. em Maybe  here you see you, do you define the same folder several times? So maybe it's a good folder to define somewhere in the top and then,  who's and so on. But oftentimes it's the DAX folder, maybe a little bit different than you expect because you forgot one level or so.  then it's super nice to just.

27:29
print out the Dex folder, see how it looks like. And you're like, m oh, okay, I'm in the wrong hierarchy basically. Yeah. So,  yeah. So I mean, now you know how to do it.  You have the video recording, how to get there.  When you have set up the package like we did correctly, and then  this installation is super easy because you just select PyTest, select the folder works. When you haven't set up the package installation correctly,

27:59
then it may mess up because maybe things that worked when you run it in the terminal, because you have set some  Python path or so in the proper way, suddenly they don't work anymore when you need to run PyTest because you run it from another folder and stuff like that. it's like, I took away some of the pain now with you or you already did yourself because you already learned before how to set up poetry and so on. But um yeah, sometimes clients had quite some issues getting just here basically.

28:28
Yeah. Oh, that's good. Yeah. like that.  Cool. So yeah, I guess then  next days,  like you started with a deck. Like, so we have a simplistic deck flow, let's say we have some first tests and like we said, can defer implementing it a little bit more sophisticated, maybe to a later point. Yeah.  You,  I, do you already have one source that you could use?

28:54
from meteorology or so, like um API where you could fetch  some data from or so because...  So I've used the oh open weather API before. yeah, I could use that. Yeah, I would say let's not make any experiments at this stage, just use something that you already use, exactly that, for example. So set it up in Python, create a DAG that just reads some data from there  and maybe save it as a CZ file locally or so. I mean, that would be already some ETL, right?

29:23
em we could do next time, could show you,  we can see how we want to proceed.  Maybe that's something we can quickly discuss now.  We can  focus first on the extraction side, maybe.  And just do all things locally. Or we could already set up maybe infrastructure on AWS or so and already em store stuff to S3, for example. So I was thinking along the lines of

29:53
kind of a medallion architecture. bronze, silver, kind of thing. And possibly so, cause I know Tom Ball of the company I'm going to, use that with iceberg. So it might be worth sort of heading down that route and yeah, setting things up that way. So even if not, think iceberg seems to be the way that people are going these days. yeah, it'd be pretty cool to do it that way.

30:22
Yeah. Yeah. Yeah. So then,  um,  so that means you would, we couldn't do that locally, I guess, first, right? So maybe avoid the complexity of the cloud first.  Yeah. Yeah. Kind of. Yeah. Yeah. Yeah. Yeah. Um, I've got AWS accounts that I can use, you know, for,  for the future, but yeah, keep things simple at the beginning. Um, I'm just wondering like, right, maybe do you have already, or maybe that's also good homework in this, in a way, um,

30:52
that you ask yourself, what are the things that I'm pretty confident about starting on the 19th? And what are some open questions or so where I'm not as confident yet. And that we focus on those things in the next Sunk sessions, basically.  like we will continue like we did now, right? So you already had some good ideas.  You can create one issue to  extract some data from the open weather API.  another issue for setting up what you just mentioned, right? The medallion structure with  iceberg.

31:22
And that's just starting like for each of these SID issues, make a new PR, quick review cycle, we merge it, keep it very simple first now,  and then we go deeper and deeper. em And that we just make sure that next week, we cover the parts where you're not so confident with yet,  that you have a good feeling starting on 19th.  And then we go deeper into all the other parts that are em ahead of us.  Yeah, yeah, sounds good. Sounds good. Cool.

31:51
um Yeah, so now it was about 30 minutes, I would say. uh It feels a bit short, but on other side, I think we  were  already available  to give them new debugging.  Yeah. Right. So I think that will make things much easier in general. um Get some clarity on what's the next steps. um And yeah, I think together with a code review that also worked already well, you created the PR.

32:20
Yeah. Now the next days we can work on something and then see what's up for Tuesday. Yeah. Yeah. Definitely good stuff. Cool. Any other questions or all clear?  No, no. I watched the Zenopython that you did with Bob. I liked that. was good.  It actually clarified some of the kind of points  really well that I kind  of didn't understand.  The one key takeaway.

32:50
was the part about shipping code because  I've got a massive problem about being a perfectionist. I go far too, I get far too hung up on things being perfect  before I'll kind of ship it.  And I really need to stop doing that.  Yeah. Likewise. I I've got much better with this, but have

33:16
I guess still have the same weakness. And I mean, I studied physics, right? So I come from this background of trying to really understand stuff and being technically correct and stuff like that.  if you go all the way to the other side of entrepreneurial, like I want to say stuff before I even touch the keyboard, but building it, you know, like I want to first get signal that people actually want to give me money for this. And then I start to think about how to solve  it. So it's like very, very.

33:45
Different  aspects. Yeah. Yeah. Cool. So, nice meeting again. Looking forward to see you again on Tuesday.  And I guess we keep it the same way. We aim for 30 minutes. If we do 40, no problem. But that's our hard cut.  It's  fun. Great. Have a good weekend. Likewise. See you. Cheers. Bye bye.

