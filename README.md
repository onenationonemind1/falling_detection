# Graduation project
[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/fDKr2SA9F2I/0.jpg)](https://www.youtube.com/watch?v=fDKr2SA9F2I)
<br/>☝️Click the Image and Enjoy the video!
# 0. Contents
1. Introduce <br/><br/>
2. Motivation <br/> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;- Why do we detect falling down? <br/><br/>
3. Solution  <br/> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;- Technologies and Libraries Used  <br/> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ‧ mediapipe ‧ opencv  <br/> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;- Establish hypotheses and explain basic logic <br/> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;      ‧ How do you measure falls? <br/> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;- Heinrich's law <br/> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    ‧ If you almost fall more than 300 times, it becomes a major disaster in the future. <br/> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;- perspective <br/> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ‧ A method for measuring the fall of distant and near objects.
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ‧ How to Calculate Falls by Region.

---
# 1. Introduce
<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fbpq8mS%2FbtsmzHE3Loy%2FhfaQx6mxhMdp9ggF2FIDi0%2Fimg.png"/>
① You can check distance between foot C.G and body C.G <br/>
② It's body center of gravity <br/>
③ It's foot center of gravity <br/>
④ You can check the count of how many times he fell. <br/>
⑤ If distance over 90 pixel(tall * 0.75), It displays he falling. <br/>
⑥ 1) Body C.G and foot C.G.  &nbsp;&nbsp;&nbsp;&nbsp;   2) Only use X axis. &nbsp;&nbsp;&nbsp;&nbsp;    3) I use this distance difference to basis of judgment <br/>
⑦ It indicates if he woke up. (This only displays after falling.) <br/>
⑧ A count of 1 goes up in the area where you fell (the count is determined by which area your feet are in). <br/>



---
## 2. Motivation
### Why do we detect falling down?
<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F6xzj5%2FbtsmsSVhMuv%2Fwjch07bNAeKD5NIYU46Cm1%2Fimg.png"/>

### According to WHO
<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbRKr2P%2FbtsmyvFurj1%2FeIZAsnyePrkAeJjG0S8EuK%2Fimg.png"/> 
Source URL : <a href="https://www.who.int/news-room/fact-sheets/detail/falls">Go WHO-Fall section</a><br>
  - Falls are the second leading cause of unintentional injury deaths worldwide. <br/>
  - Each year an estimated 684 000 individuals die from falls globally of which over 80% are in low- and middle-income countries. <br/>
  - Adults older than 60 years of age suffer the greatest number of fatal falls. <br/>
  - 37.3 million falls that are severe enough to require medical attention occur each year. <br/>
  - Prevention strategies should emphasize education, training, creating safer environments, prioritizing fall-related research and establishing &nbsp;&nbsp;&nbsp;&nbsp; effective policies to reduce risk. <br/>


---
## 3. Solution
### - Technologies and Libraries Used <br/>
<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fdkxf50%2FbtsmzZZRsSi%2FO6VcQ9i3r4r0juHg6PCS1k%2Fimg.png" width="300" />

#### Mediapipe <br/>
I used <a href="https://developers.google.com/mediapipe/solutions/vision/pose_landmarker"> Media Pipe - Pose Estimation </a> from google. <br/>
The MediaPipe Pose Landmarker task lets you detect landmarks of human bodies in an image or video.
<br/>

#### OpenCV <br/>
It is used to draw a line, draw a dot, and decorate the user's UI.
<br/>
<br/>
<br/>

### - Establish hypotheses and explain basic logic
#### How do you measure falls?
<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FGVEMn%2FbtsmzjYPyED%2Fvctb0qUjmXlTNfPDwHueKk%2Fimg.png"/>

#### How to find body's center of gravity?
<br>
Firstly, you should know how to find lectangle's center of gravity.
<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FqIaBn%2FbtsmOLVz49r%2FNewBdeQfuGdePGKFJsfAk1%2Fimg.png"/>
EXAMPLE
<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FRYCQa%2FbtsmOLBiOck%2FjACYhrvkDbR2Gq1ktjFEY0%2Fimg.png"/>


In this way you can find the center of gravity of the following body parts.
Because the human body can be divided into segments. <br/>
Source URL: <a href="https://www.digitalengineering247.com/article/human-body-thermoregulation-model-integrated-with-sc-tetra-cfd-software/cfd">Visit digitalengineering247.com!</a>

<img src="https://blog.kakaocdn.net/dn/luAyK/btsmROje1bL/mt4jx6yE1kKLMEKlpALkoK/img.png"/>

<br>
<br>

#### Finally, we can see an example based on the previous theory..
<br>
[Find C.G of left amr] <br>
<img  src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FHEX4f%2FbtsmGikM872%2FgbPKYTKyAUHDGQsVqHj86k%2Fimg.png"/>
<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbMC2Ou%2FbtsmF6EQ7LM%2F0HvOUgXxOw2kk4yKfF1JUK%2Fimg.png"/>

<br/>
Finally, We can find body's center of gravity. <br/>

<img src="https://blog.kakaocdn.net/dn/PFNCm/btsmUwbhUqA/9yyXpkgO8T1d6MLSuXLt40/img.png"/>


#### Heinrich law (Reason of mesuring count)
<img src="https://upload.wikimedia.org/wikipedia/commons/6/61/Heinrich%27s_triangle_English.png" width="300"/>

According to Heinrich's Law, when a person falls more than 300 times in the same place, it leads to one serious accident. Therefore, by counting the number of falls, we need to take action before the count exceeds 300.

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbFJlqp%2FbtsmN5e6fnR%2FgnrpG6FQ6mqnBBYA8ROPE0%2Fimg.png"/>

The above workers have experienced a fall at the site. <br/>
But most people don't take it seriously. <br/>
There are safety managers, but they have to manage too many areas. <br/>
So, task managers often install safety devices after a major accident. <br/>

<img src="https://blog.kakaocdn.net/dn/A7cHz/btsmO5GFHaR/kEqSKN1iienzTwiXZnD2pk/img.png"/>
- 20-30 km of management area per capita -> outside the scope of ability <br/>
- When working indoors, it is difficult to check CCTV in real time due to paperwork. <br/>

### Perspective
#### A method for measuring the fall of distant and near objects.  <br/>

We know that near and far objects have different sizes. <br/>
<img src="https://blog.kakaocdn.net/dn/dzVMaF/btsmRqiLjU6/Drfck2O3n4n8GUstVNWj1k/img.png"/>
<br/>

So, when measuring the fall, when measuring the length, you can solve it as follows. <br/>
Person's body of C.G * 0.75 > |body of C.G's X axis - Center of the two feet X axis|

<img src="https://blog.kakaocdn.net/dn/bmaOJk/btsmROcS6HQ/1Hi3HmOGZc6A30l5Nkjfek/img.png"/>

#### How to Calculate Falls by Region. <br/>
<br>
Examply, If you want to recognize when the center point of the feet is in the example square box, you can find out by checking if it is within the following range.
<br>

![image](https://github.com/onenationonemind1/falling_detection/assets/93633207/e2aa63d7-45bd-4228-a18f-d832f57a53ef)

<br>
<br>
So we can checke if it is within the following range.
Real region(red)

![image](https://github.com/onenationonemind1/falling_detection/assets/93633207/69831da3-cbe1-477b-be97-c13f32d16b7e)
<br>
express in code (632 line)
```
if Point_of_action_X <  320 and Point_of_action_X > 100 and  Point_of_action_Y > 390 and Point_of_action_Y > y and  standing and stage == 'falling':               
    cv2.putText(image, 'fall' , ( 320,240 ),cv2.FONT_HERSHEY_SIMPLEX, 2, (0,0,255), 2, cv2.LINE_AA )
    stage = "standing"
    counter_three +=1
```


---




