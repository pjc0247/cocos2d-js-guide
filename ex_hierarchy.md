ex_hierarchy
====
![ex_h](ex_hierarchy.gif)<br>
<br>
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
  },
  
  onMouseDown:function(e) {
    var pos = e.getLocation();
    var _this = e.getCurrentTarget();

    bubble = cc.Sprite.create("bubble.png");
    var center = bubble.getContentSize();
    text = cc.LabelTTF.create("Hello");
    text.setFontSize(20);
    text.setColor(cc.color.BLACK);
    text.setPosition(center.width/2, center.height/2 + 25);
        
    bubble.setPosition(pos);
    bubble.setScale(0);

    // 커졌다 작아지는 액션을 재생합니다.
    bubble.runAction(
      cc.Sequence.create(
        cc.ScaleTo.create(0.3, 1.2), // 처음 0.3초간 1.2배로 커짐
        cc.DelayTime.create(0.2), // 커진 상태에서 0.2초 대기
        cc.ScaleTo.create(0.13, 0), // 다시 0.13초간 사라짐
        cc.RemoveSelf.create() // 삭제
      ));

    // 텍스트를 버블노드 아래에 놓습니다.
    //   이 때문에 버블 노드에 적용한 애니메이션은
    //   텍스트 노드에도 영향을 끼칩니다.
    bubble.addChild(text);
    _this.addChild(bubble);
  },
  onMouseUp:function(e) {
  },
  onMouseMove:function(e) {
  }
});
```
