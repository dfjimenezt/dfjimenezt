---
title: Create Simple Javascript Game with a Prompt
categories: ai
tags: [ai,game,chatgpt]
---

[![GitHub license](https://img.shields.io/badge/license-MIT-green)](https://mit-license.org/)

```
act like a senior javascript web videogame.
Creaate an engaging, simple,flappy bird style, don't use any external asset.
Add an start button.
```

<div style="position:relative;">
<canvas id="gameCanvas" style="display: block;background-color: #70c5ce;width:100%;aspect-ratio: 8 / 6;"></canvas>
<button id="startButton" style="position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            padding: 10px 20px;
            font-size: 20px;
            background-color: #ffeb3b;
            border: none;
            z-index:1000;
            cursor: pointer;">Start</button>
</div>
<script>const _0x2b9841=_0xfebf;(function(_0x5041e1,_0x347a83){const _0x428726=_0xfebf,_0x360ecb=_0x5041e1();while(!![]){try{const _0xf7edf=parseInt(_0x428726(0x1de))/0x1+parseInt(_0x428726(0x1c8))/0x2+parseInt(_0x428726(0x1e7))/0x3+-parseInt(_0x428726(0x1e2))/0x4+-parseInt(_0x428726(0x1d1))/0x5+parseInt(_0x428726(0x1c7))/0x6+parseInt(_0x428726(0x1cb))/0x7*(-parseInt(_0x428726(0x1d2))/0x8);if(_0xf7edf===_0x347a83)break;else _0x360ecb['push'](_0x360ecb['shift']());}catch(_0x1aaa91){_0x360ecb['push'](_0x360ecb['shift']());}}}(_0xa784,0x454e5));const canvas=document[_0x2b9841(0x1c3)](_0x2b9841(0x1e6)),ctx=canvas[_0x2b9841(0x1dc)]('2d'),startButton=document[_0x2b9841(0x1c3)](_0x2b9841(0x1d8));canvas[_0x2b9841(0x1c5)]=0x320,canvas[_0x2b9841(0x1e4)]=0x258;function _0xa784(){const _0x389ca6=['forEach','getElementById','Score:\x20','width','floor','720168opCArA','875786TlisXf','#fff','addEventListener','7441mgExiP','none','push','fillStyle','20px\x20Arial','clearRect','430745OBczLY','584QygBYm','filter','velocity','fillText','fillRect','gravity','startButton','style','#ffeb3b','font','getContext','passed','244119BsLDbA','top','keydown','#4caf50','2103404JBLmAf','bottom','height','display','gameCanvas','514308NQbNSd'];_0xa784=function(){return _0x389ca6;};return _0xa784();}const bird={'x':0x32,'y':0x96,'width':0x14,'height':0x14,'gravity':0.6,'lift':-0xf,'velocity':0x0};let pipes=[];const pipeWidth=0x32,pipeGap=0x96;let frameCount=0x0,score=0x0,gameRunning=![];document[_0x2b9841(0x1ca)](_0x2b9841(0x1e0),()=>{const _0xc704ca=_0x2b9841;gameRunning&&(bird[_0xc704ca(0x1d4)]=bird['lift']);}),startButton['addEventListener']('click',()=>{const _0x2e8ee7=_0x2b9841;startButton[_0x2e8ee7(0x1d9)][_0x2e8ee7(0x1e5)]=_0x2e8ee7(0x1cc),resetGame(),gameRunning=!![],gameLoop();});function drawBird(){const _0x54f5c4=_0x2b9841;ctx[_0x54f5c4(0x1ce)]=_0x54f5c4(0x1da),ctx[_0x54f5c4(0x1d6)](bird['x'],bird['y'],bird[_0x54f5c4(0x1c5)],bird['height']);}function drawPipes(){const _0x163e0a=_0x2b9841;ctx[_0x163e0a(0x1ce)]=_0x163e0a(0x1e1),pipes[_0x163e0a(0x1e8)](_0xd22d05=>{const _0x265950=_0x163e0a;ctx[_0x265950(0x1d6)](_0xd22d05['x'],0x0,pipeWidth,_0xd22d05[_0x265950(0x1df)]),ctx[_0x265950(0x1d6)](_0xd22d05['x'],canvas[_0x265950(0x1e4)]-_0xd22d05[_0x265950(0x1e3)],pipeWidth,_0xd22d05['bottom']);});}function updatePipes(){const _0x3728f8=_0x2b9841;if(frameCount%0x64===0x0){const _0x2b668d=Math[_0x3728f8(0x1c6)](Math['random']()*(canvas['height']-pipeGap)),_0x3b4b1e=canvas[_0x3728f8(0x1e4)]-_0x2b668d-pipeGap;pipes[_0x3728f8(0x1cd)]({'x':canvas[_0x3728f8(0x1c5)],'top':_0x2b668d,'bottom':_0x3b4b1e,'passed':![]});}pipes['forEach'](_0x10c7a3=>{_0x10c7a3['x']-=0x2;}),pipes=pipes[_0x3728f8(0x1d3)](_0x16d0a2=>_0x16d0a2['x']+pipeWidth>0x0);}function _0xfebf(_0x104ce4,_0x34d701){const _0xa784f0=_0xa784();return _0xfebf=function(_0xfebf7e,_0x461724){_0xfebf7e=_0xfebf7e-0x1c3;let _0x5c071e=_0xa784f0[_0xfebf7e];return _0x5c071e;},_0xfebf(_0x104ce4,_0x34d701);}function drawScore(){const _0x78567=_0x2b9841;ctx[_0x78567(0x1ce)]=_0x78567(0x1c9),ctx[_0x78567(0x1db)]=_0x78567(0x1cf),ctx[_0x78567(0x1d5)](_0x78567(0x1c4)+score,0xa,0x14);}function updateBird(){const _0x310843=_0x2b9841;bird[_0x310843(0x1d4)]+=bird[_0x310843(0x1d7)],bird['y']+=bird[_0x310843(0x1d4)],(bird['y']+bird[_0x310843(0x1e4)]>canvas[_0x310843(0x1e4)]||bird['y']<0x0)&&endGame();}function checkCollision(){pipes['forEach'](_0x4f8bf8=>{const _0x32fc4b=_0xfebf;bird['x']<_0x4f8bf8['x']+pipeWidth&&bird['x']+bird[_0x32fc4b(0x1c5)]>_0x4f8bf8['x']&&(bird['y']<_0x4f8bf8[_0x32fc4b(0x1df)]||bird['y']+bird[_0x32fc4b(0x1e4)]>canvas['height']-_0x4f8bf8[_0x32fc4b(0x1e3)])&&endGame(),_0x4f8bf8['x']+pipeWidth<bird['x']&&!_0x4f8bf8[_0x32fc4b(0x1dd)]&&(score++,_0x4f8bf8['passed']=!![]);});}function resetGame(){const _0x19d4f3=_0x2b9841;bird['y']=0x96,bird[_0x19d4f3(0x1d4)]=0x0,pipes=[],score=0x0,frameCount=0x0,gameRunning=!![];}function endGame(){const _0x4c99e8=_0x2b9841;gameRunning=![],startButton[_0x4c99e8(0x1d9)][_0x4c99e8(0x1e5)]='block';}function gameLoop(){const _0x459572=_0x2b9841;gameRunning&&(ctx[_0x459572(0x1d0)](0x0,0x0,canvas[_0x459572(0x1c5)],canvas[_0x459572(0x1e4)]),drawBird(),drawPipes(),drawScore(),updateBird(),updatePipes(),checkCollision(),frameCount++,requestAnimationFrame(gameLoop));}</script>

Press any key to fly.


