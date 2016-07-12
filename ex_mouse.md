ex_mouse_move
====
![ex_mouse](ex_mouse.gif)<br>
마우스 클릭을 이용하여 캐릭터를 움직이는 예제입니다.
<br><br>
```js
var MyScene = cc.Scene.extend({
  onEnter:function () {
    this._super();
    
    cc.eventManager.addListener({
      event: cc.EventListener.MOUSE,
      onMouseDown : this.onMouseDown,
      onMouseUp : this.onMouseUp,
      onMouseMove : this.onMouseMove
    }, this);

    this.player = cc.Sprite.create("ch.png");
    this.player.setPosition(200, 200);
    this.addChild(this.player);
  },
  
  onMouseDown:function(e) {
    var loc = e.getLocation();
    var _this = e.getCurrentTarget();

    _this.player.runAction(
      cc.MoveTo.create(0.2, loc));
  },
  onMouseUp:function(e) {
  },
  onMouseMove:function(e) {
  }
});
```
