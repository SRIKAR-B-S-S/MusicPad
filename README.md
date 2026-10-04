# MusicPad

<img width="1920" height="898" alt="image" src="https://github.com/user-attachments/assets/e364d0f7-19ef-45ba-bbe4-071d380227db" />

A one-line DataURI micro-app for making music. MusicPad features 6 different sounds - KICK, SNARE, HI-HAT, PIANO, BASS and ELECTRO, it comes with a very minimal user interface. MusicPad runs without relying on any external assets or resources such as CDN, audio etc and runs on a single line of Data URI. You can directly paste it in your browser and use it. As it doesn't use any external sources, you can even use it offline!

## How to Use
You can directly paste the below Data URI in your browser and enjoy MusicPad

```data:text/html,<body style="margin:0; background:%231f1f1f;"><canvas id="c"></canvas><script>const t=c.getContext("2d");c.width=window.innerWidth,c.height=window.innerHeight;const l=(c.width-460)/2,e=(c.height-270)/2,o=[{label:"KICK",color:"%23ffe066"},{label:"SNARE",color:"%23ffb347"},{label:"HI-HAT",color:"%23ff6b6b"},{label:"PIANO",color:"%23b19ffb"},{label:"BASS",color:"%2374c0fc"},{label:"ELECTRO",color:"%23dbe4ff"}];let i=-1;const n=t=>{const n=c.getBoundingClientRect(),h=(t.clientX||t.touches&&t.touches[0].clientX)-n.left,r=(t.clientY||t.touches&&t.touches[0].clientY)-n.top;o.forEach((t,o)=>{const c=o%253,n=Math.floor(o/3),s=l+160*c,a=e+145*n;h>=s&&h<=s+140&&r>=a&&r<=a+125&&(i=o,f(),setTimeout(()=>{i=-1,f()},100))})};function f(){t.fillStyle="%231f1f1f",t.fillRect(0,0,c.width,c.height),o.forEach((o,c)=>{const n=c%253,f=Math.floor(c/3),h=i===c?4:0,r=l+160*n+h,s=e+145*f+h;t.fillStyle="%231a1a1a",t.strokeStyle=o.color,t.lineWidth=3,t.fillRect(r,s,140,125),t.strokeRect(r,s,140,125),t.fillStyle=o.color,t.font="bold 15px sans-serif",t.textAlign="center",t.fillText(o.label,r+70,s+62.5+5)}),t.strokeStyle="%23444",t.lineWidth=2,t.strokeRect(l-20,e-20,500,310),t.fillStyle="%23339af0",t.font="30px cursive",t.textAlign="center",t.fillText("Music Pad",c.width/2,e+270+65)}window.onclick=n,window.ontouchstart=n,f();</script></body>```
## Building
In case you are here to test out the files of my project, 
1. Download the files of this repo into a folder (or clone them using Git Desktop)
2. The index.html file is in the root directory itself(if you want to make any changes in the code you can do it here)
3. Open the terminal(I use VSC, so you can use the [Ctrl+`] hotkey), and type "cd shrink-js".
4. After the terminal is in the '/shrink-js' directory, you can type 'node build.mjs' which will build the index.html in the main directory into a Data URI format and put it in /result/URI.txt. You can now access the final Data URI(converted from the index.html) here!
-----
### Credits
Thanks to [this guide](https://shrink.hackclub.com/app/guides/setup) for helping me on getting started with this project.