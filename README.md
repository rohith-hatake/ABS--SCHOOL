
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Feedback & Admin Dashboard | ABS Global Smart School</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<style>
:root {
    --primary: #2563eb;
    --secondary: #0f172a;
    --accent: #10b981;
    --light: #f8fafc;
    --gray: #94a3b8;
}
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
body {
    background: linear-gradient(135deg, #0f172a, #1e293b);
    color: white;
    min-height: 100vh;
    padding: 20px;
}
.container {
    max-width: 900px;
    margin: 0 auto;
}
header {
    text-align: center;
    padding: 30px 0;
}
.logo {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 15px;
    margin-bottom: 15px;
}
.logo i {
    font-size: 2.5rem;
    color: var(--accent);
}
.logo h1 {
    font-size: 2.2rem;
    font-weight: 700;
}
.logo span {
    color: var(--accent);
}
.subtitle {
    color: var(--gray);
    font-size: 1.1rem;
    margin-top: 10px;
}
.card {
    background: rgba(30, 41, 59, 0.7);
    backdrop-filter: blur(10px);
    border-radius: 16px;
    padding: 30px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    margin-bottom: 30px;
}
.section-title {
    font-size: 1.5rem;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
}
.section-title i {
    color: var(--accent);
}
.form-group {
    margin-bottom: 20px;
}
label {
    display: block;
    margin-bottom: 8px;
    font-weight: 500;
}
input, select, textarea {
    width: 100%;
    padding: 14px;
    border-radius: 10px;
    border: 1px solid #334155;
    background: #1e293b;
    color: white;
    font-size: 1rem;
    transition: all 0.3s;
}
input:focus, select:focus, textarea:focus {
    outline: none;
    border-color: var(--accent);
    box-shadow: 0 0 0 3px rgba(16, 185, 129, 0.2);
}
textarea {
    min-height: 120px;
    resize: vertical;
}
.rating {
    display: flex;
    gap: 8px;
    margin-top: 8px;
}
.star {
    font-size: 1.8rem;
    cursor: pointer;
    color: #cbd5e1;
    transition: all 0.2s;
}
.star.active, .star:hover {
    color: #fbbf24;
}
.btn {
    background: var(--primary);
    color: white;
    border: none;
    padding: 14px 28px;
    font-size: 1.1rem;
    font-weight: 600;
    border-radius: 10px;
    cursor: pointer;
    width: 100%;
    transition: all 0.3s;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
}
.btn:hover {
    background: #1d4ed8;
    transform: translateY(-2px);
}
.btn i {
    font-size: 1.2rem;
}
.success-message {
    display: none;
    background: rgba(16, 185, 129, 0.2);
    border: 1px solid var(--accent);
    border-radius: 10px;
    padding: 15px;
    text-align: center;
    margin-top: 20px;
    animation: fadeIn 0.5s;
}
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
}
.required::after {
    content: " *";
    color: #ef4444;
}
footer {
    text-align: center;
    margin-top: 30px;
    color: var(--gray);
    font-size: 0.9rem;
}
.dashboard {
    display: none;
}
table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 10px;
}
th, td {
    border-bottom: 1px solid #334155;
    padding: 10px;
    text-align: left;
}
th {
    background: rgba(16, 185, 129, 0.2);
    color: var(--accent);
}
tr:hover {
    background: rgba(255,255,255,0.05);
}
.back-btn {
    background: var(--primary);
    padding: 10px 16px;
    border-radius: 8px;
    color: white;
    text-decoration: none;
    display: inline-block;
    margin-bottom: 15px;
}
.back-btn:hover {
    background: #1d4ed8;
}
@media (max-width: 600px) {
    .logo h1 { font-size: 1.8rem; }
    .card { padding: 20px; }
}
</style>
</head>
<body>
<div class="container">
    <header>
        <div class="logo">
            <i class="fas fa-graduation-cap"></i>
            <h1>ABS Global Smart School</h1>
        </div>
        <p class="subtitle">Computer Science Exhibition 2025 • Feedback Portal</p>
    </header>

    
    <main id="feedbackSection">
        <div class="card">
            <h2 class="section-title"><i class="fas fa-comments"></i> Share Your Feedback</h2>
            <form id="feedbackForm">
                <div class="form-group">
                    <label for="visitorType" class="required">I am a:</label>
                    <select id="visitorType" required>
                        <option value="">Select your role</option>
                        <option value="student">Student</option>
                        <option value="teacher">Teacher</option>
                        <option value="parent">Parent</option>
                        <option value="judge">Exhibition Judge</option>
                        <option value="guest">Guest/Visitor</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="name" class="required">Name</label>
                    <input type="text" id="name" placeholder="e.g., Ali Raza, Ms. Fatima, Dr. Hassan" required>
                </div>

                <div class="form-group">
                    <label>Overall Experience</label>
                    <div class="rating" id="experienceRating">
                        <i class="far fa-star star" data-value="1"></i>
                        <i class="far fa-star star" data-value="2"></i>
                        <i class="far fa-star star" data-value="3"></i>
                        <i class="far fa-star star" data-value="4"></i>
                        <i class="far fa-star star" data-value="5"></i>
                    </div>
                    <input type="hidden" id="experienceScore" value="3">
                </div>

                <div class="form-group">
                    <label for="suggestions">Suggestions for Improvement</label>
                    <textarea id="suggestions" placeholder="How can we enhance future exhibitions?"></textarea>
                </div>

                <div class="form-group">
                    <label for="highlight">Most Impressive Project & Why</label>
                    <textarea id="highlight" placeholder="e.g., The 'AI-Powered Study Buddy' stood out because..."></textarea>
                </div>

                <div class="form-group">
                    <label>
                        <input type="checkbox" id="anonymous">
                        Submit anonymously (your name won’t be saved)
                    </label>
                </div>

                <button type="submit" class="btn"><i class="fas fa-paper-plane"></i> Submit Feedback</button>
            </form>

            <div id="successMessage" class="success-message">
                <i class="fas fa-check-circle fa-2x" style="color: var(--accent); margin-bottom: 10px;"></i>
                <h3>Thank You!</h3>
                <p>Your feedback helps us shape the future of CS education at ABS Global Smart School.</p>
            </div>
        </div>

        <div style="text-align:center;">
            <button class="btn" onclick="requestAdminPassword()"><i class="fas fa-lock"></i> Admin Dashboard</button>
        </div>
    </main>

    
    <section id="adminDashboard" class="dashboard">
        <a href="#" class="back-btn" onclick="showForm()"><i class="fas fa-arrow-left"></i> Back to Feedback</a>
        <h2 class="section-title"><i class="fas fa-table"></i> Feedback Dashboard</h2>
        <div class="card">
            <table id="feedbackTable">
                <thead>
                    <tr>
                        <th>#</th>
                        <th>Role</th>
                        <th>Name</th>
                        <th>Experience</th>
                        <th>Suggestions</th>
                        <th>Highlight</th>
                        <th>Date</th>
                    </tr>
                </thead>
                <tbody></tbody>
            </table>
            <p id="noData" style="text-align:center;color:var(--gray);margin-top:10px;">No feedback submitted yet.</p>
        </div>
    </section>

    <footer>
        <p>© 2025 ABS Global Smart School • Computer Science Department</p>
    </footer>
</div>

<script>

const stars = document.querySelectorAll('.star');
const experienceScore = document.getElementById('experienceScore');
stars.forEach(star => {
    star.addEventListener('click', () => {
        const value = star.getAttribute('data-value');
        experienceScore.value = value;
        stars.forEach(s => {
            s.classList.toggle('fas', s.getAttribute('data-value') <= value);
            s.classList.toggle('far', s.getAttribute('data-value') > value);
            s.classList.toggle('active', s.getAttribute('data-value') <= value);
        });
    });
});


document.getElementById('feedbackForm').addEventListener('submit', function(e) {
    e.preventDefault();

    const visitorType = document.getElementById('visitorType').value;
    const name = document.getElementById('name').value.trim();
    const anonymous = document.getElementById('anonymous').checked;

    if (!visitorType) return alert('⚠ Please select your role.');
    if (!name && !anonymous) return alert('⚠ Please enter your name or choose anonymous.');

    const feedback = {
        visitorType,
        name: anonymous ? 'Anonymous' : name,
        experience: experienceScore.value,
        suggestions: document.getElementById('suggestions').value,
        highlight: document.getElementById('highlight').value,
        date: new Date().toLocaleString()
    };

    const list = JSON.parse(localStorage.getItem('feedbacks')) || [];
    list.push(feedback);
    localStorage.setItem('feedbacks', JSON.stringify(list));

    document.getElementById('successMessage').style.display = 'block';
    this.reset();

    stars.forEach(s => s.classList.add('far'));
    stars.forEach(s => s.classList.remove('fas', 'active'));
    experienceScore.value = '3';
});

function requestAdminPassword() {
    const password = prompt("Enter Admin Password:");
    if (password === "abs2025") {
        showDashboard();
    } else if (password !== null) {
        alert("❌ Incorrect password. Access denied!");
    }
}

function showDashboard() {
    document.getElementById('feedbackSection').style.display = 'none';
    document.getElementById('adminDashboard').style.display = 'block';

    const feedbacks = JSON.parse(localStorage.getItem('feedbacks')) || [];
    const tbody = document.querySelector('#feedbackTable tbody');
    tbody.innerHTML = '';

    if (feedbacks.length === 0) {
        document.getElementById('noData').style.display = 'block';
        return;
    }
    document.getElementById('noData').style.display = 'none';

    feedbacks.forEach((f, i) => {
        const row = document.createElement('tr');
        row.innerHTML = `
            <td>${i + 1}</td>
            <td>${f.visitorType}</td>
            <td>${f.name}</td>
            <td>${'⭐'.repeat(f.experience)}</td>
            <td>${f.suggestions || '-'}</td>
            <td>${f.highlight || '-'}</td>
            <td>${f.date}</td>
        `;
        tbody.appendChild(row);
    });
}
function showForm() {
    document.getElementById('feedbackSection').style.display = 'block';
    document.getElementById('adminDashboard').style.display = 'none';
}
</script>
</body>
</html>
