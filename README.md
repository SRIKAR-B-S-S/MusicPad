# MusicPad

<img width="1920" height="898" alt="image" src="https://github.com/user-attachments/assets/e364d0f7-19ef-45ba-bbe4-071d380227db" />

A one-line DataURI micro-app for making music. MusicPad features 6 different sounds - KICK, SNARE, HI-HAT, PIANO, BASS and ELECTRO, it comes with a very minimal user interface. MusicPad runs without relying on any external assets or resources such as CDN, audio etc and runs on a single line of Data URI. You can directly paste it in your browser and use it. As it doesn't use any external sources, you can even use it offline!

Data URI of MusicPad is only 2.38Kb!

## How to Use
You can directly paste the below Data URI in your browser and enjoy MusicPad

```data:text/html,<body style="margin:0; background:%231f1f1f;"><canvas id="c"></canvas><script>const e=c.getContext("2d");c.width=window.innerWidth,c.height=window.innerHeight;const t=(c.width-460)/2,l=(c.height-270)/2,n=[{label:"KICK",color:"%23ffe066"},{label:"SNARE",color:"%23ffb347"},{label:"HI-HAT",color:"%23ff6b6b"},{label:"PIANO",color:"%23b19ffb"},{label:"BASS",color:"%2374c0fc"},{label:"ELECTRO",color:"%23dbe4ff"}];let o,i=-1;const a=e=>{const a=c.getBoundingClientRect(),f=(e.clientX||e.touches&&e.touches[0].clientX)-a.left,s=(e.clientY||e.touches&&e.touches[0].clientY)-a.top;n.forEach((e,n)=>{const c=n%253,a=Math.floor(n/3),u=t+160*c,h=l+145*a;f>=u&&f<=u+140&&s>=h&&s<=h+125&&(i=n,function(e){o=new window.AudioContext;const t=o.currentTime,l=o.createGain();if(l.connect(o.destination),1===e||2===e){const n=o.createBuffer(1,o.sampleRate,o.sampleRate),i=n.getChannelData(0);for(let e=0;e<i.length;e++)i[e]=2*Math.random()-1;const c=o.createBufferSource(),a=o.createBiquadFilter();c.buffer=n,a.type="highpass",a.frequency.value=2===e?7e3:1e3,c.connect(a),a.connect(l),l.gain.setValueAtTime(.5,t),l.gain.exponentialRampToValueAtTime(1e-4,t+.18),c.start(t)}else{const n=o.createOscillator();n.connect(l),0===e?(n.frequency.setValueAtTime(150,t),n.frequency.exponentialRampToValueAtTime(30,t+.3),l.gain.setValueAtTime(1,t)):3===e?(n.type="triangle",n.frequency.value=523,l.gain.setValueAtTime(.4,t)):4===e?(n.type="sawtooth",n.frequency.setValueAtTime(110,t),n.frequency.exponentialRampToValueAtTime(30,t+.25),l.gain.setValueAtTime(.5,t)):5===e&&(n.type="square",n.frequency.setValueAtTime(1200,t),n.frequency.exponentialRampToValueAtTime(50,t+.12),l.gain.setValueAtTime(.2,t)),l.gain.exponentialRampToValueAtTime(.001,t+.3),n.start(t),n.stop(t+3)}}(n),r(),setTimeout(()=>{i=-1,r()},100))})};function r(){e.fillStyle="%231f1f1f",e.fillRect(0,0,c.width,c.height),n.forEach((n,o)=>{const c=o%253,a=Math.floor(o/3),r=i===o?4:0,f=t+160*c+r,s=l+145*a+r;e.fillStyle="%231a1a1a",e.strokeStyle=n.color,e.lineWidth=3,e.fillRect(f,s,140,125),e.strokeRect(f,s,140,125),e.fillStyle=n.color,e.font="bold 15px sans-serif",e.textAlign="center",e.fillText(n.label,f+70,s+62.5+5)}),e.strokeStyle="%23444",e.lineWidth=2,e.strokeRect(t-20,l-20,500,310),e.fillStyle="%23339af0",e.font="30px cursive",e.textAlign="center",e.fillText("Music Pad",c.width/2,l+270+65)}window.onclick=a,window.ontouchstart=a,r();</script></body>```

## Building
In case you are here to test out the files of my project,  
1. Download the files of this repo into a folder (or clone them using Git Desktop)
2. The index.html file is in the root directory itself(if you want to make any changes in the code you can do it here)
3. Open the terminal(I use VSC, so you can use the [Ctrl+`] hotkey), and type "cd shrink-js".
4. Make sure you have Node.js installed and run the below commands: <br> `npm init` 	`npm install --save-dev terser`
5. After the terminal is in the '/shrink-js' directory, you can type 'node build.mjs' which will build the index.html in the main directory into a Data URI format and put it in /result/URI.txt. You can now access the final Data URI(converted from the index.html) here!

## Gallery
<details>
    <summary>MusicPad</summary>
    <img width="1920" height="898" alt="image" src="https://github.com/user-attachments/assets/e364d0f7-19ef-45ba-bbe4-071d380227db" />
</details>
<details>
  <summary>Pressdown Effects</summary>
  <img width="800" height="450" alt="MusicPad" src="https://github.com/user-attachments/assets/1d348a90-2237-437e-9488-f75551c27139" />
</details>
<details>
    <summary>Initial Sketch</summary>
    <img width="2722" height="1585" src="https://github.com/user-attachments/assets/96dc4677-05cc-4ae6-98dd-12c4eb2bf4d2" />
</details>

### Credits
Thanks to [this guide](https://shrink.hackclub.com/app/guides/setup) for helping me on getting started with this project.