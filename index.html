from flask import Flask, render_template, request, redirect, session
import sqlite3
import os

app = Flask(__name__)
app.secret_key = "secret123"

# 🔐 دخول الأدمن
@app.route('/', methods=['GET', 'POST'])
def login():
    if request.method == 'POST':
        user = request.form['username']
        password = request.form['password']

        if user == "admin" and password == "1234":
            session['admin'] = True
            return redirect('/dashboard')
        else:
            return "بيانات خاطئة"

    return render_template('login.html')


# 🏠 لوحة التحكم
@app.route('/dashboard')
def dashboard():
    if 'admin' not in session:
        return redirect('/')

    conn = sqlite3.connect("database.db")
    cur = conn.cursor()
    cur.execute("SELECT * FROM children")
    data = cur.fetchall()
    conn.close()

    return render_template('dashboard.html', children=data)


# ➕ إضافة طفل
@app.route('/add', methods=['GET', 'POST'])
def add():
    if 'admin' not in session:
        return redirect('/')

    if request.method == 'POST':
        name = request.form['name']
        national_id = request.form['national_id']
        image = request.files['image']

        os.makedirs("static/images", exist_ok=True)

        filename = image.filename
        image.save("static/images/" + filename)

        conn = sqlite3.connect("database.db")
        cur = conn.cursor()
        cur.execute("INSERT INTO children (name, national_id, image) VALUES (?, ?, ?)",
                    (name, national_id, filename))
        conn.commit()
        conn.close()

        return redirect('/dashboard')

    return render_template('add_child.html')


# 🚪 خروج
@app.route('/logout')
def logout():
    session.clear()
    return redirect('/')


if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000, debug=True)
