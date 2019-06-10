# PataTab
This is Test
Ok This is my first commit to github
Im going to explain javascript part in header.
The HTML part is complicated hahaha


//first part of the inline javascript is dictionary for all keys on keyboard and we assign mp3 songs 
//and color to it
var keyData = {
			q: {
				sound: new Howl({
		  		urls: ['sounds/bubbles.mp3']
				}),
				color: '#1abc9c'
			},
			///
			w: {
				sound: new Howl({
		  		urls: ['sounds/clay.mp3']
				}),
				color: '#2ecc71'
			},
			//
			e: {
				sound: new Howl({
		  		urls: ['sounds/confetti.mp3']
				}),
				color: '#3498db'
			},
			r: {
				sound: new Howl({
		  		urls: ['sounds/corona.mp3']
				}),
				color: '#9b59b6'
			},
				t: {
				sound: new Howl({
		  		urls: ['sounds/dotted-spiral.mp3']
				}),
				color: '#34495e'
			},
			y: {
				sound: new Howl({
		  		urls: ['sounds/flash-1.mp3']
				}),
				color: '#16a085'
			},
			u: {
				sound: new Howl({
		  		urls: ['sounds/flash-2.mp3']
				}),
				color: '#27ae60'
			},
			i: {
				sound: new Howl({
		  		urls: ['sounds/flash-3.mp3']
				}),
				color: '#2980b9'
			},
			o: {
				sound: new Howl({
					urls: ['sounds/glimmer.mp3']
				}),
				color: '#8e44ad'
			},
			p: {
				sound: new Howl({
		  		urls: ['sounds/moon.mp3']
				}),
				color: '#2c3e50'
			},
			a: {
				sound: new Howl({
		  		urls: ['sounds/pinwheel.mp3']
				}),
				color: '#f1c40f'
			},
			s: {
				sound: new Howl({
		  		urls: ['sounds/piston-1.mp3']
				}),
				color: '#e67e22'
			},
				d: {
				sound: new Howl({
		  		urls: ['sounds/piston-2.mp3']
				}),
				color: '#e74c3c'
			},
			f: {
				sound: new Howl({
		  		urls: ['sounds/prism-1.mp3']
				}),
				color: '#95a5a6'
			},
			g: {
				sound: new Howl({
		  		urls: ['sounds/prism-2.mp3']
				}),
				color: '#f39c12'
			},
			h: {
				sound: new Howl({
		  		urls: ['sounds/prism-3.mp3']
				}),
				color: '#d35400'
			},
			j: {
				sound: new Howl({
		  		urls: ['sounds/splits.mp3']
				}),
				color: '#1abc9c'
			},
			k: {
				sound: new Howl({
		  		urls: ['sounds/squiggle.mp3']
				}),
				color: '#2ecc71'
			},
			l: {
				sound: new Howl({
		  		urls: ['sounds/strike.mp3']
				}),
				color: '#3498db'
			},
			z: {
				sound: new Howl({
		  		urls: ['sounds/suspension.mp3']
				}),
				color: '#9b59b6'
			},
			x: {
				sound: new Howl({
		  		urls: ['sounds/timer.mp3']
				}),
				color: '#34495e'
			},
			c: {
				sound: new Howl({
		  		urls: ['sounds/ufo.mp3']
				}),
				color: '#16a085'
			},
			//
			v: {
				sound: new Howl({
		  		urls: ['sounds/veil.mp3']
				}),
				color: '#27ae60'
			},
			//
			b: {
				sound: new Howl({
		  		urls: ['sounds/wipe.mp3']
				}),
				color: '#2980b9'
			},
			//
			n: {
				sound: new Howl({
					urls: ['sounds/zig-zag.mp3']
				}),
				color: '#8e44ad'
			},
			//
			m: {
				sound: new Howl({
		  		urls: ['sounds/moon.mp3']
				}),
				color: '#2c3e50'
			}
		}


//Creating empty array of string 
var circles = [];


//creating function for onKeyDown...
	function onKeyDown(event){
  
    //if key was press
		if(keyData[event.key]){
    
    // find max point on screen and also generate random Point ===> maxPoint x randomPoint = Point
		var maxPoint = new Point(view.size.width, view.size.height);
		var randomPoint = Point.random();
		var point = maxPoint * randomPoint;
    
    //creating newcircle with center of point and radius of 500
    
		var newCircle = new Path.Circle(point, 500)
    //give color to circle
		newCircle.fillColor = keyData[event.key].color;
    //play sound 
		keyData[event.key].sound.play();
    
    //pushing out circle obj into circle array
		circles.push(newCircle);
	   }
    }
    
  function onFrame(event){
    	for(var i = 0; i< circles.length; i++){
    		console.log(circles[i])
    		circles[i].fillColor.hue += 1
    		circles[i].scale(0.9);
    	}
    	// animatedCircle.fillColor.hue += 1;
    	// animatedCircle.scale(0.9);
    }
