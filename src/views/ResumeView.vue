<template>
    <section class="resume">
        <div class="section">
            <h2>Personal Information</h2>
            <div class="info-item">
                <strong>Name:</strong> 王駿睿 (Wang Jun Rui)
            </div>
            <div class="info-item">
                <strong>Email:</strong> aa0970606353@gmail.com
            </div>
            <div class="info-item">
                <strong>Phone:</strong> 0970606353
            </div>
            <div class="info-item">
                <strong>Location:</strong> Taiwan/ New Taipei
            </div>
        </div>

        <div class="section">
            <h2>Experience</h2>
            <div class="job">
                <h3>Fullstack Developer</h3>
                <p><strong>Company:</strong> Fenri</p>
                <p><strong>Duration:</strong> 2024 - 2025/3</p>
                <p><strong>Description:</strong> Worked on Front-end Back-end, refactoring the entire architecture.</p>
            </div>
            <div class="job">
                <h3>Tutor</h3>
                <p><strong>School:</strong> XYZ Solutions</p>
                <p><strong>Duration:</strong> 2022 - 2023</p>
                <p><strong>Description:</strong> Taught Data Structure, Algorithm, and System Design.</p>
            </div>
        </div>

        <div class="section">
            <h2>Skills</h2>
            <ul>
                <li>Languages: Go, JavaScript/TypeScript, Python, C, C++, Java</li>
                <li>Database: PostgreSQL, MongoDB, MySQL</li>
                <li>Tools: Docker, Git</li>
            </ul>
        </div>

        <div class="section">
            <h2>Education</h2>
            <p><strong>Degree:</strong> Bachelor's in Computer Science</p>
            <p><strong>Institution:</strong> National Chung Cheng University</p>
            <p><strong>Year:</strong> 2019 - 2023</p>
        </div>
    </section>
</template>

<style scoped>
.resume {
    padding: 2rem 3rem;
    background: #f8f9fa;
    font-family: 'Arial', sans-serif;
    max-width: 900px;
    margin: 0 auto;
    border-radius: 10px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.title {
    text-align: center;
    font-size: 3rem;
    margin-bottom: 2rem;
    color: #333;
}

.section {
    margin-bottom: 2rem;
}

h2 {
    font-size: 2rem;
    margin-bottom: 1rem;
    color: #2c3e50;
    border-bottom: 2px solid #ddd;
    padding-bottom: 5px;
}

h3 {
    font-size: 1.6rem;
    color: #34495e;
    margin-bottom: 0.5rem;
}

p {
    font-size: 1.1rem;
    color: #555;
    line-height: 1.6;
    margin-bottom: 0.5rem;
}

ul {
    list-style-type: none;
    padding-left: 0;
}

ul li {
    font-size: 1.1rem;
    color: #555;
    margin-bottom: 0.5rem;
}

.info-item {
    font-size: 1.1rem;
    color: #555;
    margin-bottom: 0.5rem;
    line-height: 1.5;
}
</style>
