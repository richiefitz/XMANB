# XMANB
<!DOCTYPE HTML>
<html>
<head>
    <title>Xma and Beatz</title>
    <meta name="author" content="Richie itz" />
    <meta name="date" content="april 11" />
    
    <script src="js/ToneR11.js"></script>
    <script src="js/nexusUI-v1.js"></script>

    <style>
        body, html {
            width: 100%;
            height: 100%;
            background-color: rgb(105,105,105);
        }
    
    img{
         border-color: rgb(120,120,120);
         border-style: outset;
         display: block;
         margin-left: auto;
         margin-right: auto;
        
    }
    
    .tab {
        background-color: #555;
        color: white;
        float: left;
        border: none;
        outline: none;
        cursor: pointer;
        padding: 14px 16px;
        font-size: 30px;
        text-align:center;
        width: 29%;
        font-family:'impact';
        margin-left: auto;
        }
    
    #Header1:hover{
         background-color: rgb(120,120,120);
    }
    #Header2:hover{
        background-color: rgb(120,120,120);
    }
    #Header3:hover{
        background-color: rgb(120,120,120);
    }
    
    a:link {
        text-decoration: none;
        color: white;
    }
    a:hover {
        color: hotpink;
    }
    a:visited {
        color: white;
    }
    
  
        div#controlsArea {
            width: 45%;
            height: 70%;
            margin-top: 70px;
            position: absolute;
        }


        canvas[ nx= "meter"] {
            height: 80%;
            width: 10%;
            
        }
        
        canvas[nx="slider"] {
        height: 80%;
        width: 10%;
    }
        canvas[nx="toggle"] {
        height: 20%;
        width: 30%;
        position:absolute;
    }
    
    div#padArea {
        float: top;
        height: 70%;
        margin-top: 70px;
        background-color: rgb(211,211,211);
        left: 30% ;
        position: absolute;
        font-family: 'impact';
        border-color: rgb(190,190,190);
        border-style: outset;
        
    }
    div#lowerpads {
       margin-top:10px;
    }
    div#pad2Area{
        float: top;
        height: 70%;
        margin-top: 70px;
        background-color: rgb(211,211,211);
        left: 30% ;
        position: absolute;
        font-family: 'impact';
        border-color: rgb(190,190,190);
        border-style: outset;
        margin-top:600px;
    }
    button.drumPad {
        height: 200px;
        width: 160px;
        font-family: 'impact';
        margin: 3px;
        background-color: rgb(180,180,180);
        font-size: 3em;
        border-color: rgb(190,190,190);
        border-style: outset;
    }
    
    
    div#audioElements {
        visibility: hidden;
        background-color: rgb(200,240,200);
    }
    
   
   
    </style>
    
</head>
<body id="mainBody" width="100%" height="100%">


  <div class="Title-Image">
      <img src="TitlePG.png" alt="Xma N Beatz" border="10" style="width:950px;">
    </div>
  
  <div id="Header1" class="tab">
       <a href="index.html">Looper</a>
  </div>
  <div id="Header2" class="tab">
      
      <a href="Learn.html">Learn</a>
  </div>
  <div id="Header3" class="tab">
      <a href="MPC.html">MPC</a>
  </div>
  
  
  

  <div id="controlsArea">
    <canvas nx="meter"></canvas>
    <canvas nx="slider" label="Pitch"></canvas>
    <canvas nx="toggle" label="Start/Stop"></canvas>
  </div>
  
  
  <div id="padArea" width="40%" align: "left">
      <h2>Trigger pads</h2>
      <button id="pad1" class="drumPad">1</button>
      <button id="pad2" class="drumPad">2</button>
      <button id="pad3" class="drumPad">3</button>
      <button id="pad4" class="drumPad">4</button>
      <div id="lowerpads" align: "left">
          <button id="pad5" class="drumPad">5</button>
          <button id="pad6" class="drumPad">6</button>
          <button id="pad7" class="drumPad">7</button>
          <button id="pad8" class="drumPad">8</button>
      </div>
  </div>
  <div id="pad2Area" width="40%" align: "left">
      <h2>Naked Drums</h2>
      <button id="pad9" class="drumPad">1</button>
      <button id="pad10" class="drumPad">2</button>
      <button id="pad11" class="drumPad">3</button>
      <button id="pad12" class="drumPad">4</button>
      <div id="lowerpads" align: "left">
          <button id="pad13" class="drumPad">5</button>
          <button id="pad14" class="drumPad">6</button>
          <button id="pad15" class="drumPad">7</button>
          <button id="pad16" class="drumPad">8</button>
      </div>
  </div>
  
  
          
  <script>
   
   
    // loads Loops 1-8
    var Loop1 = new Tone.Player("BoomBap_Loop.wav");
    Loop1.loop = true;
    Loop1.connect(Tone.Master);
    var Loop2 = new Tone.Player("Funk_Party_Loop.wav");
    Loop2.loop = true;
    Loop2.connect(Tone.Master);
    var Loop3 = new Tone.Player("Big_Julian_Loop.wav");
    Loop3.loop = true;
    Loop3.connect(Tone.Master);
    var Loop4 = new Tone.Player("Ghostwriter_Loop.wav");
    Loop4.loop = true;
    Loop4.connect(Tone.Master);
    var Loop5 = new Tone.Player("Hot_Pants_Loop.wav");
    Loop5.loop = true;
    Loop5.connect(Tone.Master);
    var Loop6 = new Tone.Player("Full_Clip_Loop.wav");
    Loop6.loop = true;
    Loop6.connect(Tone.Master);
    var Loop7 = new Tone.Player("Brap_Beat_Loop.wav");
    Loop7.loop = true;
    Loop7.connect(Tone.Master);
    var Loop8 = new Tone.Player("That_Sound_Loop.wav");
    Loop8.loop = true;
    Loop8.connect(Tone.Master);
    
    // loads Loops 9-16
    var Loop9 = new Tone.Player("BoomBap_Loop_Drums.wav");
    Loop9.loop = true;
    Loop9.connect(Tone.Master);
    var Loop10 = new Tone.Player("Funk_Party_Loop_Drums.wav");
    Loop10.loop = true;
    Loop10.connect(Tone.Master);
    var Loop11 = new Tone.Player("Big_Julian_Loop_Drums.wav");
    Loop11.loop = true;
    Loop11.connect(Tone.Master);
    var Loop12 = new Tone.Player("Ghostwriter_Loop_Drums.wav");
    Loop12.loop = true;
    Loop12.connect(Tone.Master);
    var Loop13 = new Tone.Player("Hot_Pants_Loop_Drums.wav");
    Loop13.loop = true;
    Loop13.connect(Tone.Master);
    var Loop14 = new Tone.Player("Full_Clip_Loop_Drums.wav");
    Loop14.loop = true;
    Loop14.connect(Tone.Master);
    var Loop15 = new Tone.Player("Brap_Beat_Loop_Drums.wav");
    Loop15.loop = true;
    Loop15.connect(Tone.Master);
    var Loop16 = new Tone.Player("That_Sound_Loop_Drums.wav");
    Loop16.loop = true;
    Loop16.connect(Tone.Master);
    
    
    
 
    



  
  
  var audioContext;
  if (window.AudioContext) {
      audioContext = new window.AudioContext();
  }
  else if (window.webkitAudioContext) {
      audioContext = new window.webkitAudioContext();
  }
  
  
  // CONTROLS PITCH FUNCTION
  
  var sliderActions = function(event){
      var Pitch = event.value;
      Pitch = Pitch * 2;
      console.log("pitch is " + Pitch);
      Loop1.playbackRate = Pitch;
      Loop2.playbackRate = Pitch;
      Loop3.playbackRate = Pitch;
      Loop4.playbackRate = Pitch;
      Loop5.playbackRate = Pitch;
      Loop6.playbackRate = Pitch;
      Loop7.playbackRate = Pitch;
      Loop8.playbackRate = Pitch;
      Loop9.playbackRate = Pitch;
      Loop10.playbackRate = Pitch;
      Loop11.playbackRate = Pitch;
      Loop12.playbackRate = Pitch;
      Loop13.playbackRate = Pitch;
      Loop14.playbackRate = Pitch;
      Loop15.playbackRate = Pitch;
      Loop16.playbackRate = Pitch;
      
  }
  
  /*var sliderVol = function(event){
      var vol = event.value;
      
      console.log("Volime is " + vol);
      Volume.value = vol;
  }*/
  
  
  // This function controls the toggle for On and OFF
  var toggleActions = function(event) {
      var on = event.value ;
      
      if (event.value == 1 ){
         playbackRate = 1;
         
      }
      else {
          playbackRate = 0;
          
          
      }
      
      // if the sample player isn't running yet
      if (Loop1.state == "stopped") {
          
          Loop1.volume.value = 0;
          Loop2.volume.value = 0;
          Loop3.volume.value = 0;
          Loop4.volume.value = 0;
          Loop5.volume.value = 0;
          Loop6.volume.value = 0;
          Loop7.volume.value = 0;
          Loop8.volume.value = 0;
          Loop9.volume.value = 0;
          Loop10.volume.value = 0;
          Loop11.volume.value = 0;
          Loop12.volume.value = 0;
          Loop13.volume.value = 0;
          Loop14.volume.value = 0;
          Loop15.volume.value = 0;
          Loop16.volume.value = 0;
          
      }
      else{
          Loop1.volume.value = -100;
          Loop2.volume.value = -100;
          Loop3.volume.value = -100;
          Loop4.volume.value = -100;
          Loop5.volume.value = -100;
          Loop6.volume.value = -100;
          Loop7.volume.value = -100;
          Loop8.volume.value = -100;
          Loop9.volume.value = -100;
          Loop10.volume.value = -100;
          Loop11.volume.value = -100;
          Loop12.volume.value = -100;
          Loop13.volume.value = -100;
          Loop14.volume.value = -100;
          Loop15.volume.value = -100;
          Loop16.volume.value = -100;
      }
      
  }
 
 var button1 = document.getElementById("pad1");
 button1.addEventListener("mousedown", button1Actions);
 function button1Actions(event) {
     if (Loop1) Loop1.start(0);
     
     Loop1.volume.value = 0;
     Loop2.volume.value = -100;
     Loop3.volume.value = -100;
     Loop4.volume.value = -100;
     Loop5.volume.value = -100;
     Loop6.volume.value = -100;
     Loop7.volume.value = -100;
     Loop9.volume.value = -100;
     Loop10.volume.value = -100;
     Loop11.volume.value = -100;
     Loop12.volume.value = -100;
     Loop13.volume.value = -100;
     Loop14.volume.value = -100;
     Loop15.volume.value = -100;
     Loop16.volume.value = -100;
     Loop8.volume.value = -100;
     
 }
  var button2 = document.getElementById("pad2");
  button2.addEventListener("mousedown", button2Actions);
  function button2Actions(event) {
      if (Loop2) Loop2.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = 0;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
      
  }
  var button3 = document.getElementById("pad3");
  button3.addEventListener("mousedown", button3Actions);
  function button3Actions(event) {
      if (Loop3) Loop3.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = 0;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
      
  }
  var button4 = document.getElementById("pad4");
  button4.addEventListener("mousedown", button4Actions);
  function button4Actions(event) {
      if (Loop4) Loop4.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = 0;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
      
  }
  var button5 = document.getElementById("pad5");
  button5.addEventListener("mousedown", button5Actions);
  function button5Actions(event) {
      if (Loop5) Loop5.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = 0;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
      
  }
  var button6 = document.getElementById("pad6");
  button6.addEventListener("mousedown", button6Actions);
  function button6Actions(event) {
      if (Loop6) Loop6.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = 0;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
      
  }
  var button7 = document.getElementById("pad7");
  button7.addEventListener("mousedown", button7Actions);
  function button7Actions(event) {
      if (Loop7) Loop7.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = 0;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
      
  }
  var button8 = document.getElementById("pad8");
  button8.addEventListener("mousedown", button8Actions);
  function button8Actions(event) {
      if (Loop8) Loop8.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = 0;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
      
  }
  var button9 = document.getElementById("pad9");
  button9.addEventListener("mousedown", button9Actions);
  function button9Actions(event) {
      if (Loop9) Loop9.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -0;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
      
      
  }
  var button10 = document.getElementById("pad10");
  button10.addEventListener("mousedown", button10Actions);
  function button10Actions(event) {
      if (Loop10) Loop10.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = 0;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
      
      
  }
  var button11 = document.getElementById("pad11");
  button11.addEventListener("mousedown", button11Actions);
  function button11Actions(event) {
      if (Loop11) Loop11.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = 0;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
      
      
  }
  var button12 = document.getElementById("pad12");
  button12.addEventListener("mousedown", button12Actions);
  function button12Actions(event) {
      if (Loop12) Loop12.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = 0;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
      
      
  }
  var button13 = document.getElementById("pad13");
  button13.addEventListener("mousedown", button13Actions);
  function button13Actions(event) {
      if (Loop13) Loop13.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = 0;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
      
      
  }
  var button14 = document.getElementById("pad14");
  button14.addEventListener("mousedown", button14Actions);
  function button14Actions(event) {
      if (Loop14) Loop14.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = 0;
      Loop15.volume.value = -100;
      Loop16.volume.value = -100;
  }
  var button15 = document.getElementById("pad15");
  button15.addEventListener("mousedown", button15Actions);
  function button15Actions(event) {
      if (Loop15) Loop15.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = 0;
      Loop16.volume.value = -100;
  }
  var button16 = document.getElementById("pad16");
  button16.addEventListener("mousedown", button16Actions);
  function button16Actions(event) {
      if (Loop16) Loop16.start(0);
      
      Loop1.volume.value = -100;
      Loop2.volume.value = -100;
      Loop3.volume.value = -100;
      Loop4.volume.value = -100;
      Loop5.volume.value = -100;
      Loop6.volume.value = -100;
      Loop7.volume.value = -100;
      Loop8.volume.value = -100;
      Loop9.volume.value = -100;
      Loop10.volume.value = -100;
      Loop11.volume.value = -100;
      Loop12.volume.value = -100;
      Loop13.volume.value = -100;
      Loop14.volume.value = -100;
      Loop15.volume.value = -100;
      Loop16.volume.value = 0;
      
      
  }
  
  
    // when the nexus UI system loads we call this function
    nx.onload = function() {
        toggle1.on("*", toggleActions);
        slider1.set({ value: 0.5 })
        slider1.on("*",sliderActions);


        // connect the nexus level meter to the ToneJS master output
        meter1.setup(Tone.Master.context, Tone.Master.output);
        
        // loads Loops 1-8
        var Loop1 = new Tone.Player("BoomBap_Loop.wav");
        Loop1.loop = true;
        Loop1.connect(Tone.Master);
        var Loop2 = new Tone.Player("Funk_Party_Loop.wav");
        Loop2.loop = true;
        Loop2.connect(Tone.Master);
        var Loop3 = new Tone.Player("Big_Julian_Loop.wav");
        Loop3.loop = true;
        Loop3.connect(Tone.Master);
        var Loop4 = new Tone.Player("Ghostwriter_Loop.wav");
        Loop4.loop = true;
        Loop4.connect(Tone.Master);
        var Loop5 = new Tone.Player("Hot_Pants_Loop.wav");
        Loop5.loop = true;
        Loop5.connect(Tone.Master);
        var Loop6 = new Tone.Player("Full_Clip_Loop.wav");
        Loop6.loop = true;
        Loop6.connect(Tone.Master);
        var Loop7 = new Tone.Player("Brap_Beat_Loop.wav");
        Loop7.loop = true;
        Loop7.connect(Tone.Master);
        var Loop8 = new Tone.Player("That_Sound_Loop.wav");
        Loop8.loop = true;
        Loop8.connect(Tone.Master);
        
        // loads Loops 9-16
        var Loop9 = new Tone.Player("BoomBap_Loop_Drums.wav");
        Loop9.loop = true;
        Loop9.connect(Tone.Master);
        var Loop10 = new Tone.Player("Funk_Party_Loop_Drums.wav");
        Loop10.loop = true;
        Loop10.connect(Tone.Master);
        var Loop11 = new Tone.Player("Big_Julian_Loop_Drums.wav");
        Loop11.loop = true;
        Loop11.connect(Tone.Master);
        var Loop12 = new Tone.Player("Ghostwriter_Loop_Drums.wav");
        Loop12.loop = true;
        Loop12.connect(Tone.Master);
        var Loop13 = new Tone.Player("Hot_Pants_Loop_Drums.wav");
        Loop13.loop = true;
        Loop13.connect(Tone.Master);
        var Loop14 = new Tone.Player("Full_Clip_Loop_Drums.wav");
        Loop14.loop = true;
        Loop14.connect(Tone.Master);
        var Loop15 = new Tone.Player("Brap_Beat_Loop_Drums.wav");
        Loop15.loop = true;
        Loop15.connect(Tone.Master);
        var Loop16 = new Tone.Player("That_Sound_Loop_Drums.wav");
        Loop16.loop = true;
        Loop16.connect(Tone.Master);
     
    }
  
  </script>
  
</body>
</html>


