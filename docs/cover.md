#cover
--- 
<style type="text/css">
body{position: absolute;top:0px;left:0px;width: 100%;height:100%;}
body>a{display: none;}
.ui-frozen-cover{overflow: hidden;position: absolute;top:0px;left:0px;width: 100%;height:100%;}
.item{width:100%;height:25%;display: -webkit-box;-webkit-box-pack:center; -webkit-box-align:center}
.close{position:fixed;top:10px;right:10px;display: block;width:50px;height:50px;color:#fff;border:#fff 1px solid; text-align: center;border-radius: 50px;line-height: 50px;display: none;z-index: 2000}
.title{color:#fff;display: block;text-align: center;font-size: 24px;-webkit-transition:all .5s .3s;}
.info{color:#fff;display: block;text-align: center;font-size: 12px;-webkit-transition:all .5s;top:50%;width:100%;top:50%;position: absolute;z-index: 2000;opacity: 0;-webkit-transform:translateY(50px);}
.info.show{opacity: 1;-webkit-transform:translateY(0);}
</style>
<div class="ui-frozen-cover" id="cover" data-start-pos="source" data-trigger=".item" data-dismiss=".close">
    <div class="close">关闭</div>
    <div class="item" style="background:rgb(84, 130, 243);" data-background="rgb(84, 130, 243)">
        <div class="title">网页重构</div>
    </div>
    <div class="item" style="background:rgb(246, 188, 76);" data-background="rgb(246, 188, 76)">
        <div class="title">前端开发</div>
    </div>
    <div class="item" style="background:#75D165;" data-background="#75D165">
        <div class="title">交互设计</div>
    </div>
    <div class="item" style="background:#4DB7B7;" data-background="#4DB7B7">
        <div class="title">视觉设计</div>
    </div>
</div>
<div class="text">
    <div class="info">
        <p>全球最牛网页重构</p>
    </div>
    <div class="info">
        <p>全球最牛前端开发</p>
    </div>
    <div class="info">
        <p>全球最牛交互设计</p>
    </div>
    <div class="info">
        <p>全球最牛视觉设计</p>
    </div>

</div>
<!-- JS -->
<!-- <script src="http://i.gtimg.cn/vipstyle/frozenjs/1.0.0/effect.cover.js"></script> -->
<script src="frozenjs/1.0.1/effect.cover.js"></script> 
<script type="text/javascript">
$(".ui-frozen-cover").cover({
    callback:function(type,obj){
        switch(type){
            case "show":
            covershow(obj);
            break;
            case "hide":
            coverhide(obj);
            break;
            case "hidden":
            coverhidden(obj);
            break;
            case "shown":
            covershown(obj);
            break;
        }
    }
});
function covershow(cover){
    if(!cover._isShown){
        var title=cover.currentTrigger.find('.title'),
            index=$(".item").index(cover.currentTrigger);

        title.css({
            '-webkit-transform':'translateY('+(cover.position.screenHeight/2-title.offset().top-30)+'px)'
        });
        $('.info').eq(index).css({
            "-webkit-transition-delay":".5s"
        })
        $('.info').eq(index).addClass('show');
    }
};
function coverhide(cover){
    var title=cover.currentTrigger.find('.title'),
        index=$(".item").index(cover.currentTrigger);

    title.css({
        '-webkit-transform':'translateY(0px)'
    })
    $('.info').eq(index).css({
            "-webkit-transition-delay":"0s"
        })
    $('.info').eq(index).removeClass('show');
};
function covershown(cover){
    $('.close').show();
};
function coverhidden(){
    $('.close').hide();
};
</script>
