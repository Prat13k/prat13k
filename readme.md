![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![R](https://img.shields.io/badge/-R-276DC3?style=for-the-badge&logo=r&logoColor=white)
![Machine Learning](https://img.shields.io/badge/-Machine%20Learning-10217D?style=for-the-badge&logo=scikit-learn&logoColor=F7931E)
![Deep Learning](https://img.shields.io/badge/-Deep%20Learning-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Natural Language Processing](https://img.shields.io/badge/-Natural%20Language%20Processing-7A5198?style=for-the-badge&logo=nltk&logoColor=white)
![Image Processing](https://img.shields.io/badge/-Image%20Processing-41B883?style=for-the-badge&logo=opencv&logoColor=white)
![Computer Vision](https://img.shields.io/badge/-Computer%20Vision-1D2F6F?style=for-the-badge&logo=opencv&logoColor=white)
![MySQL](https://img.shields.io/badge/-MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![MongoDB](https://img.shields.io/badge/-MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Tableau](https://img.shields.io/badge/-Tableau-E97627?style=for-the-badge&logo=tableau&logoColor=white)
![Power BI](https://img.shields.io/badge/-Power%20BI-F2C811?style=for-the-badge&logo=power-bi&logoColor=black)
![HTML](https://img.shields.io/badge/-HTML-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/-CSS-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/-Tailwind%20CSS-06B6D4?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Three.js](https://img.shields.io/badge/-Three.js-000000?style=for-the-badge&logo=three.js&logoColor=white)
![Julia](https://img.shields.io/badge/-Julia-9558B2?style=for-the-badge&logo=julia&logoColor=white)
![Blender](https://img.shields.io/badge/-Blender-F5792A?style=for-the-badge&logo=blender&logoColor=white)
![Solidity](https://img.shields.io/badge/-Solidity-363636?style=for-the-badge&logo=solidity&logoColor=white)

import matplotlib.pyplot as plt
import numpy as np
import seaborn as sns

# Folder to save images
import os
output_folder = "portfolio_graphs"
os.makedirs(output_folder, exist_ok=True)

# 1. Skill Proficiency Radar Chart
def radar_chart():
    categories = ['Python', 'Machine Learning', 'Deep Learning', 'NLP', 'Data Visualization', 'SQL', 'HTML/CSS']
    values = [9, 8, 7.5, 7, 8.5, 7, 6]
    angles = np.linspace(0, 2 * np.pi, len(categories), endpoint=False).tolist()
    values += values[:1]  # Complete the circle
    angles += angles[:1]
    
    fig, ax = plt.subplots(figsize=(6, 6), subplot_kw=dict(polar=True))
    ax.fill(angles, values, color='orange', alpha=0.25)
    ax.plot(angles, values, color='orange', linewidth=2)
    ax.set_yticks([2, 4, 6, 8])
    ax.set_yticklabels(["2", "4", "6", "8"], color="grey")
    ax.set_xticks(angles[:-1])
    ax.set_xticklabels(categories, fontsize=11, color="black")
    plt.title("Skill Proficiency Radar Chart", fontsize=16, color='orange')
    plt.savefig(f"{output_folder}/radar_chart.png")

# 2. Projects Timeline (Gantt Chart)
def gantt_chart():
    projects = ['AI Assistant', 'Stock Predictor', 'Portfolio Dashboard', 'CV System']
    start = [1, 2, 5, 7]
    duration = [1, 2, 2, 3]
    
    fig, ax = plt.subplots(figsize=(8, 4))
    ax.barh(projects, duration, left=start, color='skyblue', edgecolor='black')
    ax.set_title("Projects Timeline", fontsize=16, color='orange')
    ax.set_xlabel("Months")
    ax.set_ylabel("Projects")
    plt.savefig(f"{output_folder}/gantt_chart.png")

# 3. Language Contributions Pie Chart
def pie_chart():
    languages = ['Python', 'JavaScript', 'SQL', 'HTML/CSS', 'Other']
    contributions = [50, 20, 15, 10, 5]
    
    fig, ax = plt.subplots(figsize=(6, 6))
    ax.pie(contributions, labels=languages, autopct='%1.1f%%', startangle=140,
           colors=['#FFD700', '#6495ED', '#FF7F50', '#87CEEB', '#E6E6FA'])
    plt.title("Language Contributions", fontsize=16, color='orange')
    plt.savefig(f"{output_folder}/pie_chart.png")

# 4. GitHub Contributions Heatmap
def heatmap():
    data = np.random.randint(0, 10, size=(7, 52))  # 7 days, 52 weeks
    fig, ax = plt.subplots(figsize=(12, 6))
    sns.heatmap(data, ax=ax, cmap='YlGnBu', cbar=False, linewidths=0.1, linecolor='white')
    ax.set_title('GitHub Contributions Heatmap', fontsize=16, color='orange')
    ax.set_xlabel("Weeks")
    ax.set_ylabel("Days")
    plt.savefig(f"{output_folder}/heatmap.png")

# 5. Tech Stack Usage Over Time (Line Chart)
def line_chart():
    time = ['2020', '2021', '2022', '2023', '2024']
    python = [50, 60, 70, 85, 90]
    ml = [30, 50, 65, 80, 85]
    sql = [20, 30, 40, 50, 60]
    
    fig, ax = plt.subplots(figsize=(8, 6))
    ax.plot(time, python, label="Python", color='orange', marker='o')
    ax.plot(time, ml, label="Machine Learning", color='blue', marker='o')
    ax.plot(time, sql, label="SQL", color='green', marker='o')
    ax.set_title("Tech Stack Usage Over Time", fontsize=16, color='orange')
    ax.set_xlabel("Years")
    ax.set_ylabel("Skill Level")
    ax.legend()
    plt.savefig(f"{output_folder}/line_chart.png")

# 6. GitHub Stats Bar Chart
def bar_chart():
    categories = ['Commits', 'Repos', 'Languages']
    stats = [1200, 50, 12]
    
    fig, ax = plt.subplots(figsize=(6, 6))
    ax.bar(categories, stats, color=['#FFA07A', '#20B2AA', '#9370DB'], edgecolor='black')
    ax.set_title("GitHub Stats", fontsize=16, color='orange')
    ax.set_ylabel("Count")
    plt.savefig(f"{output_folder}/bar_chart.png")

radar_chart()
gantt_chart()
pie_chart()
heatmap()
line_chart()
bar_chart()

print(f"All graphs have been saved to the folder: {output_folder}")

