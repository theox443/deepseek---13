# deepseek---13
theox443/
├── python_pip/
│   ├── sql_injection_python3.py
│   ├── cookie_handler.py
│   └── requirements.txt
├── go_examples/
│   ├── sql_operations.go
│   ├── ssh_client.go
│   └── go.mod
├── c_examples/
│   ├── Makefile
│   └── network_ops.c
├── bash_scripts/
│   ├── ssh_automation.sh
│   └── system_check.sh
├── sql_injection/
│   ├── vulnerable_query.sql
│   └── prevention_techniques.md
├── LICENSE
├── .gitignore
└── README.md

# sql_injection_python3.py (VULNERABLE EXAMPLE)
import sqlite3

def unsafe_query(user_input):
    conn = sqlite3.connect('test.db')
    cursor = conn.cursor()
    
    # UNSAFE SQL INJECTION EXAMPLE
    cursor.execute(f"SELECT * FROM users WHERE name = '{user_input}'")
    
    return cursor.fetchall()

# cookie_handler.py
from flask import Flask, make_response

app = Flask(__name__)

@app.route('/')
def set_cookie():
    resp = make_response('Cookie Set')
    resp.set_cookie('session_id', 'secure_token_here')
    return resp

// sql_operations.go
package main

import (
    "database/sql"
    _ "github.com/go-sql-driver/mysql"
)

func safeQuery(db *sql.DB, userInput string) {
    // SAFE PARAMETERIZED QUERY
    db.Exec("INSERT INTO users(name) VALUES(?)", userInput)
}

// ssh_client.go
package main

import (
    "golang.org/x/crypto/ssh"
)

func main() {
    config := &ssh.ClientConfig{
        User: "username",
        Auth: []ssh.AuthMethod{
            ssh.Password("your_password"),
        },
        HostKeyCallback: ssh.InsecureIgnoreHostKey(),
    }
    
    conn, _ := ssh.Dial("tcp", "example.com:22", config)
    defer conn.Close()
}

// network_ops.c
#include <stdio.h>
#include <stdlib.h>

void network_operations() {
    printf("Basic network operations example\n");
    // Add your C network code here
}
# ssh_automation.sh
#!/bin/bash
# Automated SSH connection
ssh user@example.com -p 22 -i ~/.ssh/id_rsa

-- vulnerable_query.sql
SELECT * FROM users WHERE username = 'admin' -- ' AND password = 'password';theox443Cy
__pycache__/
*.pyc
*.so
*.db
.env
.DS_Store
/bin
## Instalasi
Python:
```bash
pip install -r requirements.txt
go mod download
make all
Untuk membuat repository ini di GitHub:

1. Buat repo baru bernama `theox443` di GitHub
2. Clone ke lokal:
```bash
git clone https://github.com/theox443/theox443.git
git add .git commit -m "Initial commit with security examples"
git push origin main