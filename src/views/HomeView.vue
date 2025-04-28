<script setup>
import { onMounted, ref } from 'vue';

const meteorCanvas = ref(null);

onMounted(() => {
    const canvas = meteorCanvas.value;
    const ctx = canvas.getContext('2d');
    let snowflakes = [];

    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    // 創建一個雪花
    function createSnowflake() {
        snowflakes.push({
            x: Math.random() * canvas.width,
            y: Math.random() * -canvas.height,
            radius: Math.random() * 3 + 2, // 雪花大小
            speedY: Math.random() * 1 + 0.5, // 下落速度
            speedX: Math.random() * 1 - 0.5, // 左右飄移
            opacity: Math.random() * 0.5 + 0.5, // 透明度
        });
    }

    // 畫每一個雪花
    function drawSnowflake(snowflake) {
        ctx.beginPath();
        ctx.arc(snowflake.x, snowflake.y, snowflake.radius, 0, Math.PI * 2);
        ctx.fillStyle = `rgba(255, 255, 255, ${snowflake.opacity})`;
        ctx.fill();
    }

    function animate() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        snowflakes.forEach((snowflake) => {
            drawSnowflake(snowflake);
            snowflake.x += snowflake.speedX;
            snowflake.y += snowflake.speedY;

            // 如果雪花落到底部，重置到頂端重新掉落
            if (snowflake.y > canvas.height) {
                snowflake.y = -snowflake.radius;
                snowflake.x = Math.random() * canvas.width;
            }
        });

        // 維持雪花數量
        if (snowflakes.length < 300) {
            createSnowflake();
        }

        requestAnimationFrame(animate);
    }

    animate();

    window.addEventListener('resize', () => {
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
    });
});

const projects = ref([
    {
        id: 1,
        title: 'Reta 社群網站',
        description: 'React TypeScript Go/Gin Postgresql',
        link: '#',
    },
    {
        id: 2,
        title: 'MDL 公司形象網站',
        description: 'Next.js TRPC MongoDB',
        link: '#',
    },
    {
        id: 3,
        title: '監測控制系統',
        description: 'React Python/FastAPI Mysql',
        link: '#',
    },
    {
        id: 4,
        title: '資料庫備份',
        description: 'Python Mysqlshell',
        link: '#',
    },
    {
        id: 5,
        title: '多機器學習模型',
        description: 'Resnet50 / XGBoost',
        link: '#'
    }
]);


</script>


<template>
    <section class="hero">
        <img src="@/assets/css/me.jpg" alt="Profile Photo" class="profile" data-aos="fade-up" />
        <h1 class="name" data-aos="fade-down" data-aos-delay="200">王駿睿 | Wang Jun Rui | Perry</h1>
        <div class="info" data-aos="fade-up" data-aos-delay="400">
            <p>Favorite country: <span>Taiwan</span></p>
            <p>Favorite sport: <span>Table tennis</span></p>
            <p>Favorite programming language: <span>GO</span></p>
        </div>
        <br>
        <div class="projects-container">
            <div class="card-container">
                <div v-for="project in projects" :key="project.id" class="card">
                    <h2 class="card-title">{{ project.title }}</h2>
                    <p class="card-description">{{ project.description }}</p>
                </div>
            </div>
        </div>
    </section>

    <canvas ref="meteorCanvas" class="meteor-canvas"></canvas>
</template>


<style scoped>
.hero {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 4rem 2rem;
    background: transparent;
    min-height: 100vh;
    text-align: center;
}

.profile {
    border-radius: 50%;
    width: 180px;
    height: 180px;
    object-fit: cover;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
    margin-bottom: 2rem;
}

.name {
    font-size: 2rem;
    font-weight: bold;
    margin-bottom: 1.5rem;
    color: #ffffff;
}

.info p {
    margin: 0.5rem 0;
    font-size: 1.2rem;
    color: #ffffff;
}

.info span {
    font-weight: bolder;
    color: #ffffff;
}

.title {
    font-size: 2.5rem;
    font-weight: bold;
    color: #ffffff;
    margin-bottom: 3rem;
}

.card-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 2rem;
    width: 100%;
    max-width: 1200px;
}

.card {
    background: #525151;
    padding: 2rem;
    border-radius: 30px;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
    transition: all 0.3s ease-in-out;
    cursor: pointer;
    overflow: hidden;
}


.card-title {
    font-size: 1.6rem;
    font-weight: 600;
    color: #ffffff;
    margin-bottom: 1rem;
    transition: color 0.3s ease;
}

.card-description {
    font-size: 1.1rem;
    color: #ffffff;
    margin-bottom: 1.5rem;
    line-height: 1.5;
}

.meteor-canvas {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
    background: linear-gradient(to bottom, #ffffff, rgb(75, 75, 75));
}
</style>
