<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Web前端课程作业展示</title>
    <style>
        /* 全局样式 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Microsoft YaHei', Arial, sans-serif;
        }
        
        body {
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
        }
        
        a {
            text-decoration: none;
            color: #2c3e50;
        }
        
        a:hover {
            color: #3498db;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* 头部样式 */
        header {
            background-color: #2c3e50;
            color: white;
            padding: 20px 0;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
        }
        
        .logo span {
            color: #3498db;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 20px;
        }
        
        nav ul li a {
            color: white;
            font-weight: 500;
        }
        
        
        /* 主要内容区 */
        .main-content {
            padding: 40px 0;
        }
        
        .hero {
            background-color: #3498db;
            color: white;
            padding: 60px 0;
            text-align: center;
            margin-bottom: 40px;
            border-radius: 5px;
        }
        
        .hero h1 {
            font-size: 36px;
            margin-bottom: 20px;
        }
        
               
        /* 作业展示区 */
        .assignments {
            margin-bottom: 40px;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 30px;
            position: relative;
        }
        
        .section-title h2 {
            display: inline-block;
            background-color: #f5f5f5;
            padding: 0 20px;
            position: relative;
            z-index: 1;
            color: #2c3e50;
        }
        
        .section-title::after {
            content: "";
            position: absolute;
            top: 50%;
            left: 0;
            right: 0;
            height: 1px;
            background-color: #ddd;
            z-index: 0;
        }
        
        .assignment-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
        }
        
        .assignment-card {
            background-color: white;
            border-radius: 5px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }
        
        .assignment-card:hover {
            transform: translateY(-5px);
        }
        
        .assignment-img {
            height: 160px;
            background-color: #eee;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #999;
        }
        
        .assignment-info {
            padding: 20px;
        }
        
        .assignment-info h3 {
            margin-bottom: 10px;
            color: #2c3e50;
        }
        
        .assignment-info p {
            color: #666;
            margin-bottom: 15px;
            font-size: 14px;
        }
        
        .assignment-info a {
            display: inline-block;
            background-color: #3498db;
            color: white;
            padding: 8px 15px;
            border-radius: 3px;
            font-size: 14px;
        }
        
        .assignment-info a:hover {
            background-color: #2980b9;
        }
        
        /* 关于我部分 */
        .about {
            background-color: white;
            padding: 30px;
            border-radius: 5px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
            margin-bottom: 40px;
        }
        
        .about-content {
            display: flex;
            align-items: center;
        }
        
        .about-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background-color: #eee;
            margin-right: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #999;
            flex-shrink: 0;
        }
        
        .about-text h3 {
            margin-bottom: 10px;
            color: #2c3e50;
        }
        
        .about-text p {
            color: #666;
            margin-bottom: 15px;
        }
        
        /* 页脚 */
        footer {
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 20px 0;
            font-size: 14px;
        }
        
        /* 响应式设计 */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                margin-top: 15px;
                justify-content: center;
            }
            
            nav ul li {
                margin: 0 10px;
            }
            
            .about-content {
                flex-direction: column;
                text-align: center;
            }
            
            .about-img {
                margin-right: 0;
                margin-bottom: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- 头部区域 -->
    <header>
        <div class="container header-content">
            <div class="logo">Web<span>前端</span>作业展示</div>
            <nav>
                <ul>
                    <li>首页</li>
                    <li>作业展示</li>
                    <li>关于我</li>
                    <li>联系方式</li>
                </ul>
            </nav>
        </div>
    </header>
    
    <!-- 主要内容区 -->
    <main class="main-content">
        <div class="container">
            <!-- 欢迎区域 -->
            <section id="home" class="hero">
                <h1>Web前端课程作业展示</h1>
                <p>这里展示我在Web前端开发课程中的学习成果和实践项目，包括HTML、CSS、JavaScript等技术的应用案例。</p >
            </section>
            
            <!-- 作业展示区 -->
            <section id="assignments" class="assignments">
                <div class="section-title">
                    <h2>我的作业展示</h2>
                </div>
                
                <div class="assignment-grid">
                    <!-- 作业1 -->
                    <div class="assignment-card">
                        <div class="assignment-img">HTML/CSS 网页设计</div>
                        <div class="assignment-info">
                            <h3>个人简历网页</h3>
                            <p>使用纯HTML和CSS设计的响应式个人简历网页，展示了基本的网页布局和样式设计能力。</p >
                            查看详情
                        </div>
                    </div>
                    
                    <!-- 作业2 -->
                    <div class="assignment-card">
                        <div class="assignment-img">JavaScript 应用</div>
                        <div class="assignment-info">
                            <h3>待办事项列表</h3>
                            <p>使用JavaScript实现的一个简单的待办事项管理应用，具有添加、删除和标记完成功能。</p >
                            查看详情
                        </div>
                    </div>
                    
                    <!-- 作业3 -->
                    <div class="assignment-card">
                        <div class="assignment-img">响应式设计</div>
                        <div class="assignment-info">
                            <h3>响应式博客页面</h3>
                            <p>采用响应式设计技术创建的博客页面，能够在不同设备上良好显示，使用了媒体查询等技术。</p >
                            查看详情
                        </div>
                    </div>
                    
                    <!-- 作业4 -->
                    <div class="assignment-card">
                        <div class="assignment-img">CSS3 动画</div>
                        <div class="assignment-info">
                            <h3>CSS动画效果展示</h3>
                            <p>展示了多种CSS3动画效果，包括过渡、变换和关键帧动画，增强了网页的交互体验。</p >
                            查看详情
                        </div>
                    </div>
                </div>
            </section>
            
            <!-- 关于我 -->
            <section id="about" class="about">
                <div class="about-content">
                    <div class="about-img">个人照片</div>
                    <div class="about-text">
                        <h3>关于我</h3>
                        <p>我是XX大学计算机科学与技术专业的学生，目前正在学习Web前端开发技术。通过这门课程，我掌握了HTML、CSS和JavaScript的基础知识，并能够独立完成简单的网页开发项目。</p >
                        <p>我对前端开发充满热情，喜欢将创意转化为实际的网页效果，并不断学习新的技术和工具来提升自己的开发能力。</p >
                    </div>
                </div>
            </section>
        </div>
    </main>
    
    <!-- 页脚 -->
    <footer>
        <div class="container">
            <p>© 2023 Web前端课程作业展示 | 设计开发: 你的名字</p >
            <p>联系方式: example@email.com | 课程名称: Web前端开发基础</p >
        </div>
    </footer>
</body>
</html>
