# D037 vue+django三国演义知识图谱可视化系统

> 完整项目收费，可联系QQ: 81040295 微信: mmdsj186011 注明从github来的，谢谢！
也可以关注我的B站： 麦麦大数据 https://space.bilibili.com/1583208775
> 

up主B站：  **麦麦大数据**
关注B站，有好处！

编号:  D037
## 视频
[视频链接](https://www.bilibili.com/video/BV1gC4y157Ch/)
## 1 系统简介
系统简介：本系统是一个基于Vue、Django、MySQL和Neo4j构建的《三國演義》知识图谱可视化系统，旨在为用户提供《三國演義》人物及势力的知识图谱可视化、搜索、查询和用户信息管理等功能。系统的核心功能包括：知识图谱可视化，展示《三 國 演 義》的主要人物及其之间的关联关系；人物信息管理模块，提供细致的角色信息，包含表字、效力主势力、出生地、性别、简介以及三国志11中的五维属性数值；势力查询模块，允许用户查看各个势力的成员及其详情；用户管理模块，实现用户登录、注册及个人信息的修改。该系统融合了传统数据库与图谱数据库的优势，通过可视化的方式呈现知识，提升用户的交互体验。
## 2 功能设计
该系统采用B/S架构模式，分为前端和后端两个部分。前端使用Vue.js框架构建，结合Vuex进行状态管理，Vue Router实现路由导航，ECharts用于数据可视化。后端采用Django框架构建RESTful API，处理业务逻辑，并与MySQL数据库和Neo4j图数据库进行交互。MySQL数据库主要用于存储结构化的用户信息和人物数据，Neo4j则用于存储人物之间的关系和图谱结构。系统还引入了爬虫模块，用于抓取相关数据，并通过蒸汽姿态API获取人物立绘。整个系统强调用户体验，通过统一的API接口和模块化设计，确保系统的可扩展性和维护性。
### 2.1系统架构图
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/76f4c75ed6d544caad3335b4fd6e291f.png)
### 2.2 功能模块图
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/2f601ac610264fffb4a9ad919244c656.png)
## 3 功能展示
### 3.1 登录 & 注册
登录界面背景是一个视频，展示和本文系统主题相匹配的内容，登录和注册界面在一个界面下，通过按钮来切换，注册界面输入用户名和密码，会检查这个用户是否存在，登录界面则要检查用户名是否存在以及用户名密码是否正确：  
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/f576a064d9134a18979b8d53d918fed4.png)
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/9a755d838e084ce990ff2f60862d010b.png)
### 3.2 知识图谱构造
如果通过校验，则可以进入主页，在主页是一个左侧菜单，右侧操作面板的布局，右上角是登录用户的头像和退出按钮：
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/4d322e7198c54a77b689df7334a7e5de.png)
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/8ede24b8c67d4273a4368a4f8e156d38.png)
### 3.3 知识图谱可视化
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/91fcd76f0cec4f2099e6e429f9ca0941.png)
知识图谱可视化支持搜索：
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/c61e4bbf8d1d4fa3a96d25f60825f205.png)

### 3.4 势力查询
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/536fd106a8ee4239be778f770599c4b9.png)
关于这些势力，比如魏国，可以点击查看关系图（知识图谱的子图）：
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/a52f904f7ee6499398069445e7b3b491.png)
### 3.5 人物查询
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/22e060167ede4ee6907d97ad8787e9b4.png)
输入关键词进行人物的搜索：
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/336741616b734cb8acbcb320213ecd39.png)
点击人物查看详情介绍页面：
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/221947fbba7d4f0a845900b6b069d1cf.png)
### 3.6 个人设置
个人设置方面包含了**用户信息修改**、**密码修改**功能。
用户信息修改中可以上传头像，完成用户的头像个性化设置，也可以修改用户其他信息。
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/507cdfeb2c9f4df59b97763448670204.png)
修改密码需要输入用户旧密码和新密码，验证旧密码成功后，就可以完成密码修改。
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/bb0cbe835f8f41739b2526e973c474e4.png)
## 4程序代码
### 4.1 代码说明
代码介绍：该项目旨在构建一个三国演义人物知识图谱可视化系统，利用Vue.js框架和ECharts图表库实现。系统功能包括展示人物节点、势力节点、人物间的关系，以及支持模糊查询功能。用户可以通过输入关键词查询相关人物或势力，并可视化查看其关联关系。
### 4.2 流程图
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/9846af4b19c6433aa071e5b274749307.png)
### 4.3 代码实例
```python
<script>
import echarts from 'echarts'

export default {
  data() {
    return {
      chart: null,
      search Keyword: '',
      // 示例数据结构
      nodes: [
        { id: 1, name: '关羽', category: '蜀汉' },
        { id: 2, name: '刘备', category: '蜀汉' },
        { id: 3, name: '张飞', category: '蜀汉' },
        { id: 4, name: '曹操', category: '魏国' },
        { id: 5, name: '孙权', category: '东吴' }
      ],
      links: [
        { source: 2, target: 1, name: '兄弟' },
        { source: 2, target: 3, name: '兄弟' },
        { source: 4, target: 5, name: '盟友' }
      ]
    }
  },
  mounted() {
    this.initChart()
  },
  methods: {
    initChart() {
      this.chart = echarts.init(document.getElementById('chart'))
      this.renderGraph()
    },
    renderGraph() {
      const option = {
        title: {
          text: '三国演义知识图谱'
        },
        tooltip: {},
        animation: true,
        series: [{
          type: 'graph',
          layout: 'force',
          force: {
            initLayout: 'circular'
          },
          data: this.nodes,
          links: this.links,
          categories: [
            { name: '蜀汉' },
            { name: '魏国' },
            { name: '东吴' }
          ],
          roam: true,
          label: {
            position: 'right'
          },
          lineStyle: {
            color: 'source',
            curveness: 0.3
          }
        }]
      }
      this.chart.setOption(option)
    },
    fuzzyQuery() {
      // 示例查询逻辑，可根据具体需求扩展
      const matchedNodes = this.nodes.filter(node => 
        node.name.includes(this.searchKeyword)
      )
      const matchedLinks = this.links.filter(link => 
        matchedNodes.some(node => node.id === link.source || node.id === link.target)
      )
      
      this.nodes = matchedNodes
      this.links = matchedLinks
      this.renderGraph()
    }
  }
}
</script>

```
