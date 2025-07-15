<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shefield University - Application Portal</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f5f5f5;
        }
        
        header {
            background-color: #1a3e6f;
            color: white;
            padding: 20px;
            text-align: center;
            border-radius: 5px;
            margin-bottom: 30px;
        }
        
        h1 {
            margin: 0;
            font-size: 2.2em;
        }
        
        .logo {
            height: 80px;
            margin-bottom: 10px;
        }
        
        .progress-bar {
            display: flex;
            justify-content: space-between;
            margin-bottom: 30px;
            position: relative;
        }
        
        .progress-step {
            text-align: center;
            position: relative;
            z-index: 1;
            flex: 1;
        }
        
        .step-number {
            width: 30px;
            height: 30px;
            background-color: #ddd;
            border-radius: 50%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 5px;
            font-weight: bold;
        }
        
        .step-label {
            font-size: 0.9em;
            color: #666;
        }
        
        .progress-bar::before {
            content: '';
            position: absolute;
            top: 15px;
            left: 0;
            right: 0;
            height: 2px;
            background-color: #ddd;
            z-index: 0;
        }
        
        .active .step-number {
            background-color: #1a3e6f;
            color: white;
        }
        
        .active .step-label {
            color: #1a3e6f;
            font-weight: bold;
        }
        
        .form-section {
            background-color: white;
            padding: 25px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            margin-bottom: 20px;
            display: none;
        }
        
        .form-section.active {
            display: block;
        }
        
        h2 {
            color: #1a3e6f;
            margin-top: 0;
            border-bottom: 1px solid #eee;
            padding-bottom: 10px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
        }
        
        input[type="text"],
        input[type="email"],
        input[type="tel"],
        input[type="date"],
        input[type="number"],
        select,
        textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
        }
        
        textarea {
            min-height: 100px;
            resize: vertical;
        }
        
        .form-row {
            display: flex;
            gap: 20px;
        }
        
        .form-row .form-group {
            flex: 1;
        }
        
        .btn-container {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
        }
        
        button {
            padding: 12px 25px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            transition: background-color 0.3s;
        }
        
        .btn-next {
            background-color: #1a3e6f;
            color: white;
        }
        
        .btn-next:hover {
            background-color: #0d2b52;
        }
        
        .btn-prev {
            background-color: #6c757d;
            color: white;
        }
        
        .btn-prev:hover {
            background-color: #5a6268;
        }
        
        .btn-submit {
            background-color: #28a745;
            color: white;
        }
        
        .btn-submit:hover {
            background-color: #218838;
        }
        
        .required:after {
            content: " *";
            color: red;
        }
        
        .contact-info {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 5px;
            margin-top: 30px;
            text-align: center;
        }
        
        .contact-info p {
            margin: 10px 0;
        }
        
        .contact-method {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            margin: 15px 0;
        }
        
        .contact-icon {
            width: 24px;
            height: 24px;
        }
        
        @media (max-width: 768px) {
            .form-row {
                flex-direction: column;
                gap: 0;
            }
            
            .progress-step {
                font-size: 0.8em;
            }
        }
    </style>
</head>
<body>
    <header>
        <img src="https://via.placeholder.com/80x80" alt="University Logo" class="logo">
        <h1>Shefield University Application</h1>
        <p>Please complete all sections of the application form</p>
    </header>
    
    <div class="progress-bar">
        <div class="progress-step active" id="step1">
            <div class="step-number">1</div>
            <div class="step-label">Personal Info</div>
        </div>
        <div class="progress-step" id="step2">
            <div class="step-number">2</div>
            <div class="step-label">Education</div>
        </div>
        <div class="progress-step" id="step3">
            <div class="step-number">3</div>
            <div class="step-label">Program</div>
        </div>
        <div class="progress-step" id="step4">
            <div class="step-number">4</div>
            <div class="step-label">Documents</div>
        </div>
        <div class="progress-step" id="step5">
            <div class="step-number">5</div>
            <div class="step-label">Review & Submit</div>
        </div>
    </div>
    
    <form id="applicationForm">
        <!-- Section 1: Personal Information -->
        <div class="form-section active" id="section1">
            <h2>Personal Information</h2>
            
            <div class="form-row">
                <div class="form-group">
                    <label for="firstName" class="required">First Name</label>
                    <input type="text" id="firstName" name="firstName" required>
                </div>
                <div class="form-group">
                    <label for="lastName" class="required">Last Name</label>
                    <input type="text" id="lastName" name="lastName" required>
                </div>
            </div>
            
            <div class="form-group">
                <label for="email" class="required">Email Address</label>
                <input type="email" id="email" name="email" required>
            </div>
            
            <div class="form-row">
                <div class="form-group">
                    <label for="phone" class="required">Phone Number</label>
                    <input type="tel" id="phone" name="phone" required>
                </div>
                <div class="form-group">
                    <label for="dob" class="required">Date of Birth</label>
                    <input type="date" id="dob" name="dob" required>
                </div>
            </div>
            
            <div class="form-row">
                <div class="form-group">
                    <label for="gender" class="required">Gender</label>
                    <select id="gender" name="gender" required>
                        <option value="">Select Gender</option>
                        <option value="male">Male</option>
                        <option value="female">Female</option>
                        <option value="other">Other</option>
                        <option value="prefer-not-to-say">Prefer not to say</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="nationality" class="required">Nationality</label>
                    <input type="text" id="nationality" name="nationality" required>
                </div>
            </div>
            
            <div class="form-group">
                <label for="address" class="required">Address</label>
                <textarea id="address" name="address" required></textarea>
            </div>
            
            <div class="btn-container">
                <button type="button" class="btn-next" onclick="nextSection(1)">Next</button>
            </div>
        </div>
        
        <!-- Section 2: Education Background -->
        <div class="form-section" id="section2">
            <h2>Education Background</h2>
            
            <div class="form-group">
                <label for="highSchool" class="required">High School/Secondary School Name</label>
                <input type="text" id="highSchool" name="highSchool" required>
            </div>
            
            <div class="form-row">
                <div class="form-group">
                    <label for="highSchoolYear" class="required">Year of Completion</label>
                    <input type="number" id="highSchoolYear" name="highSchoolYear" min="1900" max="2099" required>
                </div>
                <div class="form-group">
                    <label for="highSchoolGrade" class="required">Final Grade/GPA</label>
                    <input type="text" id="highSchoolGrade" name="highSchoolGrade" required>
                </div>
            </div>
            
            <div class="form-group">
                <label for="previousCollege">Previous College/University (if applicable)</label>
                <input type="text" id="previousCollege" name="previousCollege">
            </div>
            
            <div class="form-row">
                <div class="form-group">
                    <label for="collegeYears">Years Attended (if applicable)</label>
                    <input type="text" id="collegeYears" name="collegeYears" placeholder="e.g. 2018-2020">
                </div>
                <div class="form-group">
                    <label for="collegeDegree">Degree Earned (if applicable)</label>
                    <input type="text" id="collegeDegree" name="collegeDegree">
                </div>
            </div>
            
            <div class="form-group">
                <label for="qualifications">Other Qualifications/Certifications</label>
                <textarea id="qualifications" name="qualifications"></textarea>
            </div>
            
            <div class="btn-container">
                <button type="button" class="btn-prev" onclick="prevSection(2)">Previous</button>
                <button type="button" class="btn-next" onclick="nextSection(2)">Next</button>
            </div>
        </div>
        
        <!-- Section 3: Program Selection -->
        <div class="form-section" id="section3">
            <h2>Program Selection</h2>
            
            <div class="form-group">
                <label for="program" class="required">Program of Interest</label>
                <select id="program" name="program" required>
                    <option value="">Select Program</option>
                    <option value="computer-science">Computer Science</option>
                    <option value="business-administration">Business Administration</option>
                    <option value="engineering">Engineering</option>
                    <option value="medicine">Medicine</option>
                    <option value="law">Law</option>
                    <option value="arts-humanities">Arts & Humanities</option>
                    <option value="social-sciences">Social Sciences</option>
                    <option value="natural-sciences">Natural Sciences</option>
                </select>
            </div>
            
            <div class="form-group">
                <label for="degree" class="required">Degree Level</label>
                <select id="degree" name="degree" required>
                    <option value="">Select Degree Level</option>
                    <option value="bachelors">Bachelor's Degree</option>
                    <option value="masters">Master's Degree</option>
                    <option value="phd">PhD/Doctorate</option>
                    <option value="diploma">Diploma</option>
                    <option value="certificate">Certificate</option>
                </select>
            </div>
            
            <div class="form-group">
                <label for="startTerm" class="required">Preferred Start Term</label>
                <select id="startTerm" name="startTerm" required>
                    <option value="">Select Term</option>
                    <option value="fall-2023">Fall 2023</option>
                    <option value="spring-2024">Spring 2024</option>
                    <option value="summer-2024">Summer 2024</option>
                    <option value="fall-2024">Fall 2024</option>
                </select>
            </div>
            
            <div class="form-group">
                <label for="studyMode" class="required">Mode of Study</label>
                <select id="studyMode" name="studyMode" required>
                    <option value="">Select Mode</option>
                    <option value="full-time">Full-time</option>
                    <option value="part-time">Part-time</option>
                    <option value="online">Online</option>
                </select>
            </div>
            
            <div class="form-group">
                <label for="scholarship">Are you applying for any scholarships?</label>
                <select id="scholarship" name="scholarship">
                    <option value="no">No</option>
                    <option value="yes">Yes</option>
                </select>
            </div>
            
            <div class="form-group" id="scholarshipDetails" style="display:none;">
                <label for="scholarshipInfo">Scholarship Details</label>
                <textarea id="scholarshipInfo" name="scholarshipInfo"></textarea>
            </div>
            
            <div class="btn-container">
                <button type="button" class="btn-prev" onclick="prevSection(3)">Previous</button>
                <button type="button" class="btn-next" onclick="nextSection(3)">Next</button>
            </div>
        </div>
        
        <!-- Section 4: Documents -->
        <div class="form-section" id="section4">
            <h2>Documents</h2>
            
            <div class="form-group">
                <label>Documents to Upload (You can submit these later if needed)</label>
                <div style="margin-top: 15px;">
                    <div class="form-group">
                        <input type="checkbox" id="transcript" name="documents[]" value="transcript">
                        <label for="transcript" style="display: inline; font-weight: normal;">Academic Transcripts</label>
                    </div>
                    <div class="form-group">
                        <input type="checkbox" id="diploma" name="documents[]" value="diploma">
                        <label for="diploma" style="display: inline; font-weight: normal;">Diplomas/Certificates</label>
                    </div>
                    <div class="form-group">
                        <input type="checkbox" id="recommendation" name="documents[]" value="recommendation">
                        <label for="recommendation" style="display: inline; font-weight: normal;">Letters of Recommendation</label>
                    </div>
                    <div class="form-group">
                        <input type="checkbox" id="personalStatement" name="documents[]" value="personalStatement">
                        <label for="personalStatement" style="display: inline; font-weight: normal;">Personal Statement</label>
                    </div>
                    <div class="form-group">
                        <input type="checkbox" id="cv" name="documents[]" value="cv">
                        <label for="cv" style="display: inline; font-weight: normal;">CV/Resume</label>
                    </div>
                    <div class="form-group">
                        <input type="checkbox" id="passport" name="documents[]" value="passport">
                        <label for="passport" style="display: inline; font-weight: normal;">Passport Copy</label>
                    </div>
                    <div class="form-group">
                        <input type="checkbox" id="englishTest" name="documents[]" value="englishTest">
                        <label for="englishTest" style="display: inline; font-weight: normal;">English Proficiency Test (if applicable)</label>
                    </div>
                </div>
            </div>
            
            <div class="form-group">
                <label for="additionalInfo">Additional Information</label>
                <textarea id="additionalInfo" name="additionalInfo" placeholder="Any other information you'd like to share with the admissions committee"></textarea>
            </div>
            
            <div class="btn-container">
                <button type="button" class="btn-prev" onclick="prevSection(4)">Previous</button>
                <button type="button" class="btn-next" onclick="nextSection(4)">Next</button>
            </div>
        </div>
        
        <!-- Section 5: Review and Submit -->
        <div class="form-section" id="section5">
            <h2>Review Your Application</h2>
            
            <div class="form-group">
                <h3>Personal Information</h3>
                <div id="reviewPersonal"></div>
            </div>
            
            <div class="form-group">
                <h3>Education Background</h3>
                <div id="reviewEducation"></div>
            </div>
            
            <div class="form-group">
                <h3>Program Selection</h3>
                <div id="reviewProgram"></div>
            </div>
            
            <div class="form-group">
                <h3>Documents</h3>
                <div id="reviewDocuments"></div>
            </div>
            
            <div class="form-group">
                <input type="checkbox" id="declaration" name="declaration" required>
                <label for="declaration" style="display: inline; font-weight: normal;" class="required">I declare that the information provided is accurate and complete to the best of my knowledge.</label>
            </div>
            
            <div class="contact-info">
                <h3>Submit Your Application</h3>
                <p>Please submit your completed application form and contact our admissions office for next steps:</p>
                
                <div class="contact-method">
                    <img src="https://cdn-icons-png.flaticon.com/512/3670/3670051.png" alt="WhatsApp" class="contact-icon">
                    <p>WhatsApp: <a href="https://wa.me/447832714017">+447832714017</a></p>
                </div>
                
                <div class="contact-method">
                    <img src="https://cdn-icons-png.flaticon.com/512/732/732200.png" alt="Email" class="contact-icon">
                    <p>Email: <a href="mailto:Shefielduni@proton.me">Shefielduni@proton.me</a></p>
                </div>
            </div>
            
            <div class="btn-container">
                <button type="button" class="btn-prev" onclick="prevSection(5)">Previous</button>
                <button type="button" class="btn-submit" onclick="submitForm()">Submit Application</button>
            </div>
        </div>
    </form>
    
    <script>
        let currentSection = 1;
        const totalSections = 5;
        
        function nextSection(current) {
            // Validate current section before proceeding
            if (validateSection(current)) {
                document.getElementById(`section${current}`).classList.remove('active');
                document.getElementById(`step${current}`).classList.remove('active');
                
                currentSection = current + 1;
                
                document.getElementById(`section${currentSection}`).classList.add('active');
                document.getElementById(`step${currentSection}`).classList.add('active');
                
                // If moving to review section, update the review content
                if (currentSection === 5) {
                    updateReview();
                }
                
                // Scroll to top of the new section
                window.scrollTo(0, 0);
            }
        }
        
        function prevSection(current) {
            document.getElementById(`section${current}`).classList.remove('active');
            document.getElementById(`step${current}`).classList.remove('active');
            
            currentSection = current - 1;
            
            document.getElementById(`section${currentSection}`).classList.add('active');
            document.getElementById(`step${currentSection}`).classList.add('active');
            
            // Scroll to top of the new section
            window.scrollTo(0, 0);
        }
        
        function validateSection(sectionNum) {
            const section = document.getElementById(`section${sectionNum}`);
            const inputs = section.querySelectorAll('[required]');
            let isValid = true;
            
            for (let input of inputs) {
                if (!input.value) {
                    input.style.borderColor = 'red';
                    isValid = false;
                } else {
                    input.style.borderColor = '#ddd';
                }
            }
            
            if (!isValid) {
                alert('Please fill in all required fields before proceeding.');
            }
            
            return isValid;
        }
        
        function updateReview() {
            // Personal Information
            document.getElementById('reviewPersonal').innerHTML = `
                <p><strong>Name:</strong> ${document.getElementById('firstName').value} ${document.getElementById('lastName').value}</p>
                <p><strong>Email:</strong> ${document.getElementById('email').value}</p>
                <p><strong>Phone:</strong> ${document.getElementById('phone').value}</p>
                <p><strong>Date of Birth:</strong> ${document.getElementById('dob').value}</p>
                <p><strong>Gender:</strong> ${document.getElementById('gender').value}</p>
                <p><strong>Nationality:</strong> ${document.getElementById('nationality').value}</p>
                <p><strong>Address:</strong> ${document.getElementById('address').value}</p>
            `;
            
            // Education Background
            document.getElementById('reviewEducation').innerHTML = `
                <p><strong>High School:</strong> ${document.getElementById('highSchool').value} (${document.getElementById('highSchoolYear').value})</p>
                <p><strong>Grade/GPA:</strong> ${document.getElementById('highSchoolGrade').value}</p>
                ${document.getElementById('previousCollege').value ? `<p><strong>Previous College:</strong> ${document.getElementById('previousCollege').value} (${document.getElementById('collegeYears').value})</p>` : ''}
                ${document.getElementById('collegeDegree').value ? `<p><strong>Degree Earned:</strong> ${document.getElementById('collegeDegree').value}</p>` : ''}
                ${document.getElementById('qualifications').value ? `<p><strong>Other Qualifications:</strong> ${document.getElementById('qualifications').value}</p>` : ''}
            `;
            
            // Program Selection
            document.getElementById('reviewProgram').innerHTML = `
                <p><strong>Program:</strong> ${document.getElementById('program').value}</p>
                <p><strong>Degree Level:</strong> ${document.getElementById('degree').value}</p>
                <p><strong>Start Term:</strong> ${document.getElementById('startTerm').value}</p>
                <p><strong>Mode of Study:</strong> ${document.getElementById('studyMode').value}</p>
                ${document.getElementById('scholarship').value === 'yes' ? `<p><strong>Scholarship:</strong> Yes - ${document.getElementById('scholarshipInfo').value}</p>` : '<p><strong>Scholarship:</strong> No</p>'}
            `;
            
            // Documents
            let documentsList = '';
            const checkboxes = document.querySelectorAll('input[name="documents[]"]:checked');
            checkboxes.forEach(checkbox => {
                documentsList += `<li>${checkbox.nextElementSibling.textContent}</li>`;
            });
            
            document.getElementById('reviewDocuments').innerHTML = `
                <p><strong>Documents to be submitted:</strong></p>
                ${documentsList ? `<ul>${documentsList}</ul>` : '<p>No documents selected</p>'}
                ${document.getElementById('additionalInfo').value ? `<p><strong>Additional Information:</strong> ${document.getElementById('additionalInfo').value}</p>` : ''}
            `;
        }
        
        function submitForm() {
            if (validateSection(5)) {
                // Here you would normally send the form data to a server
                // For this example, we'll just show an alert
                alert('Thank you for your application! Please contact our admissions office via WhatsApp or email to complete the process.');
                
                // You could also gather all form data and display it
                const formData = new FormData(document.getElementById('applicationForm'));
                const formObject = {};
                formData.forEach((value, key) => {
                    formObject[key] = value;
                });
                
                console.log('Form data:', formObject);
                
                // In a real implementation, you would send this data to your server
                // fetch('/submit-application', {
                //     method: 'POST',
                //     body: JSON.stringify(formObject),
                //     headers: {
                //         'Content-Type': 'application/json'
                //     }
                // })
                // .then(response => response.json())
                // .then(data => {
                //     alert('Application submitted successfully!');
                // })
                // .catch(error => {
                //     console.error('Error:', error);
                //     alert('There was an error submitting your application. Please try again or contact us directly.');
                // });
            }
        }
        
        // Show/hide scholarship details based on selection
        document.getElementById('scholarship').addEventListener('change', function() {
            document.getElementById('scholarshipDetails').style.display = 
                this.value === 'yes' ? 'block' : 'none';
        });
    </script>
</body>
</html>
