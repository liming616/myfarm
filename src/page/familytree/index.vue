
<template>
<div id="container">
  <div id="graph-container"></div>
    <div class="head-menu">
        <div class="user-btn btn_bg" style="font-size: 11px; line-height: 18px;">
            <a href="/mobile/webapp/user/mycenter/foo=bar/" class="user-info">
                <i class="default-avatar icon -new-profile"></i>
            </a>
        </div>
        <div class="add-btn btn_bg" style="font-size: 11px; line-height: 18px;">

        </div>
        <div class="search-btn btn_bg" style="font-size: 11px; line-height: 18px;">

        </div>
    </div>

</div>
</template>
<style lang="scss" scoped>

  #graph-container {
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    position: absolute;
  }
  .btn_bg {
    font-size: 11px;
    line-height: 18px;

    width: 35px;
    height: 35px;
    line-height: 35px;
    text-align: center;
    background: rgba(255, 255, 255, .8);
    -webkit-box-shadow: 1px 1px 2px rgba(0, 0, 0, .4);
    border-radius: 3px;
    z-index: 0;
  }
  .default-avatar {
    margin-top: 16px;
    font-size: 18px;
    color: #fff;
  }
  .icon.-new-profile:before {
    content: "\e903";
  }
  .user-btn{
    float: left;
    margin-left: 20px;
  }
  .add-btn{
    float: right;
    margin-right: 20px;
  }
  .search-btn{
    float: right;
    margin-right: 10px;
  }
  .head-menu{
    /*display: -webkit-flex!important;*/
    display: inline-block;
    width: 100%;
    height: 35px;
    line-height: 35px;
    position: absolute;
    top: 20px;
  }
</style>
<script>

  import "./js/jquery-2.1.1.min.js"


  import "./src/sigma.core.js"
  import "./src/conrad.js"
  import "./src/utils/sigma.utils.js"
  import "./src/utils/sigma.polyfills.js"
  import"./src/sigma.settings.js"
  import "./src/classes/sigma.classes.dispatcher.js"
  import "./src/classes/sigma.classes.configurable.js"
  import "./src/classes/sigma.classes.graph.js"
  import "./src/classes/sigma.classes.camera.js"
  import "./src/classes/sigma.classes.quad.js"
  import "./src/classes/sigma.classes.edgequad.js"
  import "./src/captors/sigma.captors.mouse.js"
  import "./src/captors/sigma.captors.touch.js"
  import "./src/renderers/sigma.renderers.canvas.js"
  import "./src/renderers/sigma.renderers.webgl.js"
  import "./src/renderers/sigma.renderers.svg.js"
  import "./src/renderers/sigma.renderers.def.js"
  import "./src/renderers/webgl/sigma.webgl.nodes.def.js"
  import "./src/renderers/webgl/sigma.webgl.nodes.fast.js"
  import "./src/renderers/webgl/sigma.webgl.edges.def.js"
  import "./src/renderers/webgl/sigma.webgl.edges.fast.js"
  import "./src/renderers/webgl/sigma.webgl.edges.arrow.js"
  import "./src/renderers/canvas/sigma.canvas.labels.def.js"
  import "./src/renderers/canvas/sigma.canvas.hovers.def.js"
  import "./src/renderers/canvas/sigma.canvas.nodes.def.js"
  import "./src/renderers/canvas/sigma.canvas.edges.def.js"
  import "./src/renderers/canvas/sigma.canvas.edges.curve.js"
  import "./src/renderers/canvas/sigma.canvas.edges.arrow.js"
  import "./src/renderers/canvas/sigma.canvas.edges.curvedArrow.js"
  import "./src/renderers/canvas/sigma.canvas.edgehovers.def.js"
  import "./src/renderers/canvas/sigma.canvas.edgehovers.curve.js"
  import "./src/renderers/canvas/sigma.canvas.edgehovers.arrow.js"
  import "./src/renderers/canvas/sigma.canvas.edgehovers.curvedArrow.js"
  import "./src/renderers/canvas/sigma.canvas.extremities.def.js"
  import "./src/renderers/svg/sigma.svg.utils.js"
  import "./src/renderers/svg/sigma.svg.nodes.def.js"
  import "./src/renderers/svg/sigma.svg.edges.def.js"
  import "./src/renderers/svg/sigma.svg.edges.curve.js"
  import "./src/renderers/svg/sigma.svg.labels.def.js"
  import "./src/renderers/svg/sigma.svg.hovers.def.js"
  import "./src/middlewares/sigma.middlewares.rescale.js"
  import "./src/middlewares/sigma.middlewares.copy.js"
  import "./src/misc/sigma.misc.animation.js"
  import "./src/misc/sigma.misc.bindEvents.js"
  import "./src/misc/sigma.misc.bindDOMEvents.js"
  import "./src/misc/sigma.misc.drawHovers.js"
  import "./plugins/sigma.renderers.customShapes/shape-library.js"
  import "./plugins/sigma.renderers.customShapes/sigma.renderers.customShapes.js"

  var myNode={
    //编号
    id:1,
    //姓名
    name:"test",
    //昵称
    nickname:"test",
    //年龄
    age:30,
    //性别
    gender:"",
    //出生日期
    birthday:"",
    //属相
    born:{},
    //事迹（同一代人，或下一代直系亲属中的代表可写）
    achievement:"",
            //职业
            gender:"",
            //现住址
            birthday:"",
            //联系方式
            birthday:{
                //电话、微信、qq
            },
    //配偶myNode
    spouse:[{}],
    //孩子myNode
    children:[{}],
    //兄弟（选填）
    brothers:[{}],
    //世（根据录入情况更新）
    era:1,
    //排行
    seniority:1,
    //头像（考虑使用继承）
    img:"",
    //状态
    status:{
      //是否是根节点
      root:"",
      //是否是根节点
      leaf:"",
    },
    //备注
    remark:""
  },
  relationship={
    myNode:{},
    otherNode:{},
    relation:{}
  },

          relationEm={
               id:1,
               name:""
          },
          gender={
            man:"男",
            women:"女"
          },
          born={
//            鼠Rat、牛Ox、Tiger、Rabbit、、、、、、、、
            Rat:"鼠",
            Ox:"牛",
            Tiger:"虎",
            Rabbit:"兔",
            Dragon:"龙",
            Snake:"蛇",
            Horse:"马",
            Goat:"羊",
            Monkey:"猴",
            Rooster:"鸡",
            Dog:"狗",
            Pig:"猪"
          }


/**
 * IMPORTANT: This only works with the canvas renderer. TBD in the future
 * will also support the WebGL renderer.
 */
sigma.utils.pkg('sigma.canvas.nodes');

// generate a random graph
var i,
    s,
    img,
    N = 5,
    E = 3,
    g = {
      nodes: [],
      edges: []
    },
    urls = [
      'img/img1.png',
      'img/img2.png',
      'img/img3.png',
      'img/img4.png'
    ],
    colors = [
      '#617db4',
      '#668f3c',
      '#c6583e',
      '#b956af'
    ];
  var node1={
    //编号
    id:1,
    //姓名
    name:"李树忠",
    //昵称
    nickname:"",
    //年龄
    age:54,
    //性别
    gender:gender.man,
    //出生日期
    birthday:"1964",
    //属相
    born:born.Dragon,
    //事迹（同一代人，或下一代直系亲属中的代表可写）
    achievement:"",
    //配偶myNode
    spouse:node2,
    //配偶myNode
    otherSpouse:[],
    //父母
    parent:[{}],
    //孩子myNode
    children:[node3],
    //兄弟（选填）
    brothers:[{}],
    //世（根据录入情况更新）
    era:1,
    //排行
    seniority:1,
    //头像（考虑使用继承）
    img:"",
    //状态
    status:{
      //是否是根节点
      root:"",
      //是否是根节点
      leaf:"",
    },
    //备注
    remark:""
  },node2={
    //编号
    id:2,
    //姓名
    name:"肖淑兰",
    //昵称
    nickname:"",
    //年龄
    age:56,
    //性别
    gender:gender.women,
    //出生日期
    birthday:"1962",
    //属相
    born:born.Tiger,
    //事迹（同一代人，或下一代直系亲属中的代表可写）
    achievement:"",
    //配偶myNode
    spouse:node1,
    //配偶myNode
    otherSpouse:[],
    //父母
    parent:[{}],
    //孩子myNode
    children:[{}],
    //兄弟（选填）
    brothers:[{}],
    //世（根据录入情况更新）
    era:1,
    //排行
    seniority:1,
    //头像（考虑使用继承）
    img:"",
    //状态
    status:{
      //是否是根节点
      root:"",
      //是否是根节点
      leaf:"",
    },
    //备注
    remark:""
  },node3={
    //编号
    id:3,
    //姓名
    name:"李明",
    //昵称
    nickname:"",
    //年龄
    age:32,
    //性别
    gender:gender.man,
    //出生日期
    birthday:"1986",
    //属相
    born:born.Ox,
    //事迹（同一代人，或下一代直系亲属中的代表可写）
    achievement:"",
    //配偶myNode
    spouse:node4,
    //配偶myNode
    otherSpouse:[],
    //父母
    parent:[node1,node2],
    //孩子myNode
    children:[node5],
    //兄弟（选填）
    brothers:[{}],
    //世（根据录入情况更新）
    era:2,
    //排行
    seniority:1,
    //头像（考虑使用继承）
    img:"",
    //状态
    status:{
      //是否是根节点
      root:"",
      //是否是根节点
      leaf:"",
    },
    //备注
    remark:""
  },node4={
    //编号
    id:4,
    //姓名
    name:"刘婷婷",
    //昵称
    nickname:"",
    //年龄
    age:30,
    //性别
    gender:gender.women,
    //出生日期
    birthday:"1987",
    //属相
    born:born.Rabbit,
    //事迹（同一代人，或下一代直系亲属中的代表可写）
    achievement:"",
    //配偶myNode
    spouse:node3,
    //配偶myNode
    otherSpouse:[],
    //父母
    parent:[{}],
    //孩子myNode
    children:[node5],
    //兄弟（选填）
    brothers:[{}],
    //世（根据录入情况更新）
    era:2,
    //排行
    seniority:1,
    //头像（考虑使用继承）
    img:"",
    //状态
    status:{
      //是否是根节点
      root:"",
      //是否是根节点
      leaf:"",
    },
    //备注
    remark:""
  },node5={
      //编号
      id:5,
      //姓名
      name:"李紫嫣",
      //昵称
      nickname:"紫嫣",
      //年龄
      age:3,
      //性别
      gender:gender.women,
      //出生日期
      birthday:"2014",
      //属相
      born:born.Horse,
      //事迹（同一代人，或下一代直系亲属中的代表可写）
      achievement:"",
      //配偶myNode
      spouse:{},
      //配偶myNode
      otherSpouse:[],
      //父母
      parent:[node3,node4],
      //孩子myNode
      children:[],
      //兄弟（选填）
      brothers:[{}],
      //世（根据录入情况更新）
      era:3,
      //排行
      seniority:1,
      //头像（考虑使用继承）
      img:"",
      //状态
      status:{
          //是否是根节点
          root:"",
          //是否是根节点
          leaf:"",
      },
      //备注
      remark:""
  },node6={
      //编号
      id:6,
      //姓名
      name:"李阳",
      //昵称
      nickname:"",
      //年龄
      age:24,
      //性别
      gender:gender.women,
      //出生日期
      birthday:"1994",
      //属相
      born:born.Horse,
      //事迹（同一代人，或下一代直系亲属中的代表可写）
      achievement:"",
      //配偶myNode
      spouse:null,
      //配偶myNode
      otherSpouse:[],
      //父母
      parent:[node1,node2],
      //孩子myNode
      children:[],
      //兄弟（选填）
      brothers:[{}],
      //世（根据录入情况更新）
      era:2,
      //排行
      seniority:1,
      //头像（考虑使用继承）
      img:"",
      //状态
      status:{
          //是否是根节点
          root:"",
          //是否是根节点
          leaf:"",
      },
      //备注
      remark:""
  }
var nodes=[
  node1,node2,node3,node4,node5,node6
];
  node1.spouse = node2;
  node2.spouse = node1;
  node3.spouse = node4;
  node4.spouse = node3;

  node1.children = [node3,node6];
  node2.children = [node3,node6];
  node3.children = [node5];
  node4.children = [node5];
// Generate a random graph, going through the different shapes
for (i = 0; i < nodes.length; i++) {
  var node = {
    id: "n" + nodes[i].id,
    label: nodes[i].name,
    // note the ShapeLibrary.enumerate() returns the names of all
    // supported renderers
    type: ShapeLibrary.enumerate().map(function(s){return s.name;})[0],
    x: nodes[i].spouse?0.2:i*0.3,
    y: nodes[i].era,
    size: 0.1,
    color: colors[Math.floor(Math.random() * colors.length)],
    borderColor: colors[Math.floor(Math.random()* colors.length)]
  };

  if(Math.random()>0.75 && node.type!='pacman') { // ~0.75 of the (non-pacman)shapes will have an image
    node.image = {
      url: urls[Math.floor(Math.random() * urls.length)],
      // scale/clip are ratio values applied on top of 'size'
      scale: 1.3,
      clip: 0.85
    }
  }

  switch(node.type) {
    case "equilateral":
      node.equilateral = {
        rotate: Math.random()*45, // random rotate up to 45 deg
        numPoints: Math.round(5 + Math.random()*3)
      }
      break;
    case "star":
      node.star = {
        innerRatio: 0.4 + Math.random()*0.2,
        numPoints: Math.round(4 + Math.random()*3)
      }
      if(node.image) {
        // note clip/scale are ratio values. So we fit them to the inner ratio of the star shape
        node.image.clip = node.star.innerRatio *0.95;
        node.image.scale = node.star.innerRatio *1.2;
      }
      break;
    case "square":
    case "diamond":
      if(node.image) {
        // note clip/scale are ratio values. So we fit them to the borders of the square shape
        node.image.clip = 0.7;
      }
      break;
    case "circle":
      break;
    case "cross":
      node.cross = {
        lineWeight: Math.round(Math.random() * 5)
      }
      break;
  }
  g.nodes.push(node);
}

  $.each(nodes, function(index, value) {
    $.each(value.children, function(i, child) {
      g.edges.push({
        id: 'e' + index+i,
        source: "n" + value.id,
        target: "n" + child.id,
        size: Math.random(),
        type:"curve"
      });
    });

  });


s = new sigma({
  graph: g,
  renderer: {
    // IMPORTANT:
    // This works only with the canvas renderer, so the
    // renderer type set as "canvas" is necessary here.
    container: document.getElementById('graph-container'),
    type: 'canvas'
  },
  settings: {
    minNodeSize: 20,
    maxNodeSize: 50,
  }
});
s.bind('clickNode', function(e) {
  console.log(e.type, e.data.node.label, e.data.captor);
  alert("run in");
});
CustomShapes.init(s);
s.refresh();
</script>
