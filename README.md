# Coding-One-Final-Project

This is a URL to my Mimic project. (If there is no music, please click on the render code button to run the project again.)

https://mimicproject.com/code/30b8262f-a55c-4706-e935-e0506f4769b2



This is a URL to my project video!

https://vimeo.com/777934315



At the end of this semester, I combined the methods of making sounds that I learnt in the first two weeks with the GLSL I learnt in the last week to create a 'Visual & Auditory Fitter'. People can move the mouse to interact with the music and the different colours and shapes will help us to achieve a dynamic unity between sight and sound.
Firstly, I created a soundtrack combining what I had learnt about sound in weeks 1 and 2, using tools such as Oscillation, Sample and maxiClock. I downloaded some guitar, bass, techno and drum clips from Freesound and used if() and Math.random() to mix them together under certain conditions, and debugged them to create a rhythmic soundtrack. 
Click the Mimic URL to hear the music!

Then I used GLSL to create 8 visual effects for the music, using different functions and loops. I hope you can fork my project and uncomment some of them to see! Your mouse is a good interactive tool, you could move it with the music to change colours and shapes in the screen.
The logic of my visualisation experiment is to use sin(), cos(), tan(), atan(), fract(), pow(), ceil(), mod() and other functions to operate on st.x and st.y respectively. Then multiply them with time, mouse.x and mouse.y to achieve dynamic interaction.

The first design: 

gl_FragColor = vec4(  myCos * 2., mySin * mouse.x,  fract(mySin * time * 0.5)* 5., 1.0);

I used myCos, mySin, fract() to create a dazzling latticework image, maybe with jazz?

 <img width="791" alt="屏幕截图 2022-12-03 145428" src="https://user-images.githubusercontent.com/115037554/205522553-52684225-9176-4840-9688-91a2f8d4d67f.png">



The second design:

gl_FragColor = vec4(  abs(cos(uv.y )* time) , fract( myTan * mouse.x), mySin, 1.0);

I added tan() to the previous design to produce dazzling pink and yellow lines, which would go well with the techno music.
 
 <img width="794" alt="屏幕截图 2022-12-03 124035" src="https://user-images.githubusercontent.com/115037554/205522615-2b0a9a81-434e-4a51-9f10-f1aa752358c5.png">



The third design:

gl_FragColor = vec4( myAtan * myCos * mySin * mouse.x, 1.0 - uv.y, myPow2 , 1.0);

I added atan() and pow() functions, which produced a more variable pattern on the screen. The gradient blue and green split the screen in half, while some changing polka dots appear.

<img width="793" alt="屏幕截图 2022-12-03 134103" src="https://user-images.githubusercontent.com/115037554/205522626-5ae676dc-9e61-44a4-8d6c-1544247151d8.png">

 

The forth design:

gl_FragColor = vec4( abs(sin(myCeil * time)), myPow2 * time, myMod * mouse.x * time,1.0);

I added ceil(), mod(), pow() to create ripple shapes. The yellow-green colour is reminiscent of summer. At this moment I would like to listen to an R&B song.
 
 <img width="790" alt="屏幕截图 2022-12-03 195724" src="https://user-images.githubusercontent.com/115037554/205522640-fdc84935-71e6-4bfe-ae14-8a865a7746c6.png">

 
 

The fifth design:

gl_FragColor = vec4( mouse.x * mySin * myTan ,  myAtan, myCos / mySin, 1.0);

I tried multiplying mySin() with myTan(), which created some ovals. myCos divided by mySin also created some shuttle shapes. This image makes it looks like psychedelic guitars, new and distinctive blue-green hair and blinding lights.

<img width="793" alt="屏幕截图 2022-12-04 143001" src="https://user-images.githubusercontent.com/115037554/205522668-35a5eb3b-7cb2-44ee-b229-ffa1cacfb6b5.png">

 

The sixth design:

gl_FragColor = vec4( vec3( noise(vec2(20.0 * random(st * time) * mouse.x )* mouse.y ) ),1.0);

I added the noise() and random() before void main() to get the chaotic effect of the electronic signal disappearing. Then I added the time, mouse.x and mouse.y to do the arithmetic.

<img width="793" alt="屏幕截图 2022-12-03 161310" src="https://user-images.githubusercontent.com/115037554/205522685-33333085-168f-492e-a9ca-11abf9e9019b.png">

 

The seventh design:

gl_FragColor = vec4( color2 + color1, 1.0);
 
 <img width="793" alt="屏幕截图 2022-12-03 200340" src="https://user-images.githubusercontent.com/115037554/205522692-d81482fc-5e85-47b1-a526-73a3e156d45f.png">



This result consists of  two parts. I first created the flowing black liquid (named color1) using loop.

 <img width="792" alt="屏幕截图 2022-12-03 163523" src="https://user-images.githubusercontent.com/115037554/205522696-4c30b598-ddac-4b30-bcfa-3ff986937aa3.png">



I then used noise() and smoothstep tool to create a variation of the black and white image (named color2). Finally I added up color1 and color2.

 <img width="793" alt="屏幕截图 2022-12-03 164946" src="https://user-images.githubusercontent.com/115037554/205522703-2c3677a4-39fb-4efb-865f-0a07bc7c0f9f.png">



The eighth design:

gl_FragColor = vec4( color3 * abs(sin(time)) , color3 * abs(cos(time)), color3 * 0.8, 1.0);

I borrowed the truchetPattern() from The book of shaders and also used floor(), fract() and random() to make different lines. As the mouse moves, they can be turned into triangles.

 <img width="795" alt="屏幕截图 2022-12-04 140738" src="https://user-images.githubusercontent.com/115037554/205522713-bb8ecb0d-f9a6-47d3-969e-60efcc2684c9.png">


 <img width="791" alt="屏幕截图 2022-12-04 195116" src="https://user-images.githubusercontent.com/115037554/205522722-b7a47e17-5ca4-49be-9072-005863c7e45c.png">


 

Every experiment was full of surprises. I did the maths with different functions, not really knowing what picture I would end up creating. These random, unknown results kept me going. After a dozen experiments, I discovered that the visual and auditory senses can be close to each other and accommodate each other, that they do not correspond to each other. Different visual representations of the same piece of music combined with mouse interaction can be immersive. At the same time, the senses of sight and hearing are mutually reinforcing. When our eyes, ears and body are engaged at the same time, we can enjoy it better.

Hope you enjoy it! 

Have a good holiday! Bye! 






Reference:

https://freesound.org/search/?q=funk

https://thebookofshaders.com/

https://www.behance.net/search/projects?tracking_source=typeahead_search_direct&search=glsl



