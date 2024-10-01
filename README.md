# LocalHostPreAdvising
 PHPMYADMIN AND XAMPP (TESTING DATABASE FUNCTIONS)

CREATE TABLE courses (
    id INT AUTO_INCREMENT PRIMARY KEY,
    course_name VARCHAR(100) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);


-----------------------------------------------------------------

CREATE TABLE subjects (
    id INT AUTO_INCREMENT PRIMARY KEY,
    course_id INT NOT NULL,
    code VARCHAR(10) NOT NULL,
    type VARCHAR(50),
    units INT,
    description TEXT,
    status ENUM('Active', 'Inactive') DEFAULT 'Active',
    year ENUM('1', '2', '3', '4', 'summer') NOT NULL,
    semester ENUM('1st', '2nd') NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (course_id) REFERENCES courses(id) ON DELETE CASCADE
);
