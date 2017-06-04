<template>

<div >
  <link rel="import" href="//fonts.googleapis.com/css?family=Open+Sans:300,600,700">
  <nav id="nav">
    <ul>
      <li><a href="#top">我</a></li>
      <li><a href="#work">工作</a></li>
      <li><a href="#portfolio">资料</a></li>
      <li><a href="#contact">联系我</a></li>
    </ul>
  </nav>

  <div class="wrapper wrapper-style1 wrapper-first">
    <article class="container" id="top">
      <div class="row">
        <div class="4u">
          <span class="me image image-full"><img src="../../images/me.jpg" alt="" /></span>
        </div>
        <div class="8u">
          <header>
            <h1>Hi. 我是 <strong>臭氧</strong>.</h1>
          </header>
          <p>这是我的一块<strong>小天地</strong>, 能力在于坚持，自信才有力量，成长源于积累，我会辛勤耕耘这块土地。</p>
          <a href="#work" class="button button-big">我的成果</a>
        </div>
      </div>
    </article>
  </div>

  <div class="wrapper wrapper-style2">
    <article id="work">
      <header>
        <h2>这是我的工作成果</h2>
        <span>能力不强，踏踏实实做事，头脑不灵，堂堂正正做人</span>
      </header>
      <div class="container">
        <div class="row">
          <div class="12u">
          </div>
        </div>
        <div class="row">
          <div class="4u">
            <article class="box box-style2">
              <a href="//wqs.jd.com/smartstore/index.shtml?#nojump" class="image image-full"><img src="../../images/xgmarket.jpg" alt="" /></a>
              <h3><a href="//wqs.jd.com/smartstore/index.shtml?#nojump">京东小哥智能卖场</a></h3>
              <p>个性化推荐，精准营销.</p>
            </article>
          </div>
          <div class="4u">
            <article class="box box-style2">
              <a href="//nb.jd.com/address/add?stationId=366517" class="image image-full"><img src="../../images/ydsd.png" alt="" /></a>
              <h3><a href="//nb.jd.com/address/add?stationId=366517">移动商店</a></h3>
              <p>一小时达，极致用户体验.</p>
            </article>
          </div>
          <div class="4u">
            <article class="box box-style2">
              <a href="http://flypixel.com/wood-ui-kit/3574765984616310" class="image image-full"><img src="../../images/portfolio03.jpg" alt="" /></a>
              <h3><a href="http://flypixel.com/wood-ui-kit/3574765984616310">家谱</a></h3>
              <p>基于家族树的社交平台.</p>
            </article>
          </div>
        </div>
      </div>
      <footer>
        <p>往下看，或许有你需要的！</p>
        <a href="#portfolio" class="button button-big">我的积累</a>
      </footer>
    </article>
  </div>

  <div class="wrapper wrapper-style3">
    <article id="portfolio">
      <header>
        <h2>我的宝库.</h2>
        <span>技术的沉淀在于一点一滴的积累，个人的阅历需要日积月累的记录.</span>
      </header>
      <div class="container">
        <div class="row">
          <div class="4u">
            <section class="box box-style1">
              <span class="icon featured-icon icon-comments-alt"></span>
              <h3>大前端</h3>
              <a href="">{{bjlist[0].title}}</a>
            </section>
          </div>
          <div class="4u">
            <section class="box box-style1">
              <span class="icon featured-icon icon-file-alt"></span>
              <h3>java</h3>
              <p>Ornare nulla proin odio consequat sapien vestibulum ipsum primis sed amet consequat lorem dolore.</p>
            </section>
          </div>
          <div class="4u">
            <section class="box box-style1">
              <span class="icon featured-icon icon-thumbs-up"></span>
              <h3>随笔</h3>
              <p>Ornare nulla proin odio consequat sapien vestibulum ipsum primis sed amet consequat lorem dolore.</p>
            </section>
          </div>
        </div>
      </div>
      <footer>
        <p>Lorem ipsum dolor sit sapien vestibulum ipsum primis?</p>
        <a href="#contact" class="button button-big">Get in touch with me</a>
      </footer>
    </article>
  </div>

  <div class="wrapper wrapper-style4">
    <article id="contact">
      <header>
        <h2>Want to hire me? Get in touch!</h2>
        <span>Ornare nulla proin odio consequat  sapien vestibulum ipsum sed lorem.</span>
      </header>
      <div>
        <div class="row">
          <div class="12u">
            <form method="post" action="#">
              <div>
                <div class="row half">
                  <div class="6u">
                    <input type="text" name="name" id="name" placeholder="Name" />
                  </div>
                  <div class="6u">
                    <input type="text" name="email" id="email" placeholder="Email" />
                  </div>
                </div>
                <div class="row half">
                  <div class="12u">
                    <input type="text" name="subject" id="subject" placeholder="Subject" />
                  </div>
                </div>
                <div class="row half">
                  <div class="12u">
                    <textarea name="message" id="message" placeholder="Message"></textarea>
                  </div>
                </div>
                <div class="row">
                  <div class="12u">
                    <router-link  tag="li" :to="'/familytree/'" class="button form-button-submit">
                      Send Message
                    </router-link>
                    <a href="#" class="button button-alt form-button-reset">Clear Form</a>
                  </div>
                </div>
              </div>
            </form>
          </div>
        </div>
        <div class="row row-special">
          <div class="12u">
            <router-link  tag="li" :to="'/familytree/'" class="button form-button-submit">
              个人空间
            </router-link>
            <!--<h3>Find me on ...</h3>-->
            <!--<ul class="social">-->
              <!--<li class="twitter"><a href="http://twitter.com/n33co" class="icon icon-twitter"><span>Twitter</span></a></li>-->
              <!--<li class="facebook"><a href="#" class="icon icon-facebook"><span>Facebook</span></a></li>-->
              <!--<li class="dribbble"><a href="http://dribbble.com/n33" class="icon icon-dribbble"><span>Dribbble</span></a></li>-->
              <!--<li class="linkedin"><a href="#" class="icon icon-linkedin"><span>LinkedIn</span></a></li>-->
              <!--<li class="tumblr"><a href="#" class="icon icon-tumblr"><span>Tumblr</span></a></li>-->
              <!--<li class="googleplus"><a href="#" class="icon icon-google-plus"><span>Google+</span></a></li>-->
              <!--<li class="github"><a href="http://github.com/n33" class="icon icon-github"><span>Github</span></a></li>-->
            <!--</ul>-->
          </div>
        </div>
      </div>
      <footer>
        <p id="copyright">
          &copy; 2017 Untitled | Images: <a href="#">fotogrph</a> | Design: <a href="#">HTML5 UP</a>
        </p>
      </footer>
    </article>
  </div>
</div>
</template>
<script>

  import 'src/page/main/js/jquery.min.js'
  import 'src/page/main/js/config.js'
  import 'src/page/main/js/skel.js'
//  import 'src/page/main/css/skel-noscript.css'
  import 'src/page/main/css/style.css'
  import 'src/page/main/css/style-mobile.css'

  import {bjlistcity , hotcity} from '../../service/getData'

  export default {
    data(){
      return{
        bjlist:[]
//        title: '',   //标题
//        url: '', //链接
//        desc: "",     //描述
//        imgurl: {},   //图片链接
      }
    },

    mounted(){
      // 获取当前城市
      bjlistcity().then(res => {
        this.bjlist = res;
    });
    },

    components:{
    },

    computed:{

    },

    methods:{
      //点击图标刷新页面
      reload(){
        window.location.reload();
      }
    },
  }

</script>


