<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>BookaService | Vetted Home Services in Springs</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-blue: #0284c7;
            --primary-hover: #0369a1;
            --bg-light: #f8fafc;
            --navy-dark: #0f172a;
            --text-muted: #64748b;
            --border-color: #e2e8f0;
            --card-shadow: 0 4px 6px -1px rgba(0,0,0,0.05), 0 2px 4px -2px rgba(0,0,0,0.05);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            -webkit-font-smoothing: antialiased;
        }

        body {
            background-color: var(--bg-light);
            color: var(--navy-dark);
            padding: 0;
            margin: 0;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }

        /* Top Navigation Header */
        header {
            background-color: #ffffff;
            border-bottom: 1px solid #e2e8f0;
            padding: 14px 16px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 1000;
            width: 100%;
            box-sizing: border-box;
        }

        .logo {
            font-size: 18px;
            font-weight: 700;
            color: var(--navy-dark);
            letter-spacing: -0.5px;
        }

        .logo span {
            color: var(--primary-blue);
        }

        .nav-actions {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .back-link {
            font-size: 13px;
            font-weight: 600;
            color: var(--text-muted);
            background: none;
            border: none;
            cursor: pointer;
            display: none;
        }

        /* Main View Wrapper */
        main {
            flex: 1;
            padding: 20px 16px;
            max-width: 480px;
            width: 100%;
            margin: 0 auto;
        }

        .view-section {
            display: none;
        }

        .view-section.active {
            display: block;
        }

        /* VIEW 1: WELCOMING LANDING PAGE */
        .landing-hero {
            text-align: center;
            margin-top: 16px;
            margin-bottom: 24px;
        }

        .landing-hero h1 {
            font-size: 24px;
            font-weight: 700;
            line-height: 1.25;
            color: var(--navy-dark);
            margin-bottom: 8px;
            letter-spacing: -0.5px;
        }

        .landing-hero p {
            font-size: 14px;
            color: var(--text-muted);
            line-height: 1.4;
        }

        .safety-banner {
            background-color: #f0f9ff;
            border: 1px solid #e0f2fe;
            border-radius: 12px;
            padding: 16px;
            margin-bottom: 24px;
            font-size: 13px;
            color: #0369a1;
            line-height: 1.4;
            text-align: left;
        }

        .gateway-buttons {
            display: flex;
            flex-direction: column;
            gap: 14px;
            margin-bottom: 24px;
        }

        .btn-gateway {
            background-color: #ffffff;
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 18px;
            text-align: left;
            cursor: pointer;
            box-shadow: var(--card-shadow);
            transition: transform 0.15s ease, border-color 0.15s ease;
            width: 100%;
        }

        .btn-gateway:active {
            transform: scale(0.98);
            border-color: var(--primary-blue);
        }

        .btn-gateway h3 {
            font-size: 15px;
            font-weight: 600;
            color: var(--navy-dark);
            margin-bottom: 4px;
        }

        .btn-gateway p {
            font-size: 13px;
            color: var(--text-muted);
            line-height: 1.3;
        }

        /* VIEW 2: CATEGORIES SCREEN */
        .section-header {
            margin-bottom: 18px;
        }

        .section-header h2 {
            font-size: 20px;
            font-weight: 700;
            color: var(--navy-dark);
        }

        .section-header p {
            font-size: 13px;
            color: var(--text-muted);
            margin-top: 4px;
        }

        .categories-grid {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .category-card {
            background-color: #ffffff;
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 16px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: var(--card-shadow);
        }

        .category-card:active {
            background-color: #f8fafc;
            border-color: var(--primary-blue);
        }

        .arrow-indicator {
            color: var(--primary-blue);
            font-weight: 700;
            font-size: 16px;
        }

        /* VIEW 3: PROFILES DISPLAY ROW */
        .profiles-list {
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .profile-card {
            background-color: #ffffff;
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 16px;
            box-shadow: var(--card-shadow);
            display: flex;
            flex-direction: column;
            gap: 14px;
        }

        .profile-header {
            display: flex;
            gap: 14px;
            align-items: center;
        }

        .profile-avatar {
            width: 56px;
            height: 56px;
            background-color: #e2e8f0;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            color: var(--text-muted);
            font-size: 18px;
            flex-shrink: 0;
        }

        .profile-meta h4 {
            font-size: 15px;
            font-weight: 600;
            color: var(--navy-dark);
        }

        .profile-meta p {
            font-size: 12px;
            color: var(--text-muted);
            margin-top: 2px;
        }

        .verified-badge {
            background-color: #e0f2fe;
            color: #0369a1;
            font-size: 11px;
            font-weight: 600;
            padding: 2px 8px;
            border-radius: 20px;
            display: inline-block;
            margin-top: 4px;
        }

        .status-container {
            border-top: 1px solid var(--border-color);
            border-bottom: 1px solid var(--border-color);
            padding: 10px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 13px;
        }

        .status-pill {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .dot-available {
            width: 8px;
            height: 8px;
            background-color: #22c55e;
            border-radius: 50%;
        }

        .dot-booked {
            width: 8px;
            height: 8px;
            background-color: #94a3b8;
            border-radius: 50%;
        }

        .text-available { color: #16a34a; font-weight: 500; }
        .text-booked { color: #64748b; font-weight: 500; }

        .btn-action {
            background-color: var(--primary-blue);
            color: #ffffff;
            border: none;
            padding: 12px;
            border-radius: 8px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            width: 100%;
            text-align: center;
            transition: background 0.15s;
        }

        .btn-action:hover {
            background-color: var(--primary-hover);
        }

        /* VIEW 4: INTAKE FORMS SCREENS */
        .form-panel {
            background-color: #ffffff;
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 20px;
            box-shadow: var(--card-shadow);
        }

        .form-group {
            margin-bottom: 16px;
        }

        .form-group label {
            display: block;
            font-size: 13px;
            font-weight: 600;
            margin-bottom: 6px;
            color: var(--navy-dark);
        }

        input, select, textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid #cbd5e1;
            border-radius: 8px;
            font-size: 14px;
            outline: none;
            background-color: #ffffff;
            transition: border-color 0.15s;
        }

        input:focus, select:focus, textarea:focus {
            border-color: var(--primary-blue);
        }

        .escrow-card {
            background-color: #fffde7;
            border: 1px dashed #fbc02d;
            border-radius: 8px;
            padding: 12px;
            font-size: 12px;
            line-height: 1.4;
            margin: 16px 0;
            color: #744210;
        }

        .legal-check {
            display: flex;
            align-items: flex-start;
            gap: 10px;
            font-size: 12px;
            color: var(--text-muted);
            margin-bottom: 16px;
            line-height: 1.4;
        }

        .legal-check input {
            width: 16px;
            height: 16px;
            margin-top: 2px;
            accent-color: var(--primary-blue);
        }

        /* FOOTER EXTRACTION DRAWER */
        footer {
            margin-top: auto;
            padding: 20px 16px;
            border-top: 1px solid var(--border-color);
            background-color: #ffffff;
        }

        .accordion-trigger {
            font-size: 12px;
            font-weight: 500;
            color: var(--text-muted);
            text-align: center;
            cursor: pointer;
            user-select: none;
        }

        .accordion-details {
            font-size: 11px;
            color: var(--text-muted);
            line-height: 1.5;
            margin-top: 10px;
            display: none;
            text-align: justify;
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">Book<span>a</span>Service</div>
        <div class="nav-actions">
            <button class="back-link" id="backBtn" onclick="goBack()">&larr; Return Menu</button>
        </div>
    </header>

    <main>
        <!-- VIEW 1: WELCOMING LANDING PAGE -->
        <section id="view-landing" class="view-section active">
            <div class="landing-hero">
                <h1>Verified Local Help in Your Area</h1>
                <p>On-demand domestic cleaners, gardeners &amp; certified artisans across South Africa.</p>
            </div>

            <div class="safety-banner">
                <strong>&#128737; Area Escrow Protection:</strong> Background-checked local workers. Funds are safely held in Capitec escrow until your work is inspected and confirmed.
            </div>

            <div class="gateway-buttons">
                <button type="button" class="btn-gateway" onclick="showView('categories')">
                    <h3>Explore Service Categories &rarr;</h3>
                    <p>Cleaners, gardeners, painters, tilers and plumbers with fixed flat-rates.</p>
                </button>

                <button type="button" class="btn-gateway" onclick="showView('profiles')">
                    <h3>Browse Vetted Area Pros &rarr;</h3>
                    <p>View ratings, police-clearance badges, and live availability of local helpers.</p>
                </button>

                <button type="button" class="btn-gateway" onclick="showView('booking')">
                    <h3>Fast Direct Booking &rarr;</h3>
                    <p>Jump directly to the intake form for immediate area dispatch.</p>
                </button>
            </div>
        </section>

        <!-- VIEW 2: CATEGORIES SCREEN -->
        <section id="view-categories" class="view-section">
            <div class="section-header">
                <h2>Select a Service</h2>
                <p>Flat-rate ZAR pricing with zero surge fees. Capitec Escrow protected.</p>
            </div>

            <div class="categories-grid">
                <div class="category-card" onclick="selectCategory('Domestic Cleaner')">
                    <div>
                        <div>&#129529; Domestic Cleaner</div>
                        <small style="color: var(--text-muted);">R50 / hr (Min 4 hrs: R200)</small>
                    </div>
                    <span class="arrow-indicator">&rarr;</span>
                </div>

                <div class="category-card" onclick="selectCategory('Gardener')">
                    <div>
                        <div>&#127793; Gardener</div>
                        <small style="color: var(--text-muted);">R50 / hr (Min 4 hrs: R200)</small>
                    </div>
                    <span class="arrow-indicator">&rarr;</span>
                </div>

                <div class="category-card" onclick="selectCategory('Painter')">
                    <div>
                        <div>&#127912; Painter</div>
                        <small style="color: var(--text-muted);">R65 / hr (Min 4 hrs: R260)</small>
                    </div>
                    <span class="arrow-indicator">&rarr;</span>
                </div>

                <div class="category-card" onclick="selectCategory('Tiler')">
                    <div>
                        <div>&#129521; Tiler</div>
                        <small style="color: var(--text-muted);">R65 / hr (Min 4 hrs: R260)</small>
                    </div>
                    <span class="arrow-indicator">&rarr;</span>
                </div>

                <div class="category-card" onclick="selectCategory('Plumber / Artisan')">
                    <div>
                        <div>&#128295; Plumber or Electrician</div>
                        <small style="color: var(--text-muted);">R450 Call-out (Includes 1st hr)</small>
                    </div>
                    <span class="arrow-indicator">&rarr;</span>
                </div>
            </div>
        </section>

        <!-- VIEW 3: PROFILES DISPLAY ROW -->
        <section id="view-profiles" class="view-section">
            <div class="section-header">
                <h2>Vetted Area Professionals</h2>
                <p>Police-cleared local pros stationed throughout South African regional hubs.</p>
            </div>

            <div class="profiles-list">
                <!-- Profile 1 -->
                <div class="profile-card">
                    <div class="profile-header">
                        <div class="profile-avatar">NK</div>
                        <div class="profile-meta">
                            <h4>Nomvula Khumalo</h4>
                            <p>East Rand &bull; Domestic Cleaner</p>
                            <span class="verified-badge">&#10003; Verified Pro &bull; Police Cleared</span>
                        </div>
                    </div>
                    <div class="status-container">
                        <div class="status-pill">
                            <span class="dot-available"></span>
                            <span class="text-available">Available Today</span>
                        </div>
                        <strong>R50 / hr</strong>
                    </div>
                    <button type="button" class="btn-action" onclick="bookPro('Nomvula Khumalo', 'Domestic Cleaner', 'East Rand')">Book with Nomvula</button>
                </div>

                <!-- Profile 2 -->
                <div class="profile-card">
                    <div class="profile-header">
                        <div class="profile-avatar">SS</div>
                        <div class="profile-meta">
                            <h4>Sipho Sithole</h4>
                            <p>Johannesburg North &bull; Plumber / Artisan</p>
                            <span class="verified-badge">&#10003; Certified Artisan &bull; Red Seal</span>
                        </div>
                    </div>
                    <div class="status-container">
                        <div class="status-pill">
                            <span class="dot-available"></span>
                            <span class="text-available">Available Today</span>
                        </div>
                        <strong>R450 Call-out</strong>
                    </div>
                    <button type="button" class="btn-action" onclick="bookPro('Sipho Sithole', 'Plumber / Artisan', 'Johannesburg North')">Book with Sipho</button>
                </div>

                <!-- Profile 3 -->
                <div class="profile-card">
                    <div class="profile-header">
                        <div class="profile-avatar">BN</div>
                        <div class="profile-meta">
                            <h4>Blessing Ndlovu</h4>
                            <p>Pretoria &amp; Centurion &bull; Gardener</p>
                            <span class="verified-badge">&#10003; Verified Pro &bull; Equip Ready</span>
                        </div>
                    </div>
                    <div class="status-container">
                        <div class="status-pill">
                            <span class="dot-available"></span>
                            <span class="text-available">Available Today</span>
                        </div>
                        <strong>R50 / hr</strong>
                    </div>
                    <button type="button" class="btn-action" onclick="bookPro('Blessing Ndlovu', 'Gardener', 'Pretoria & Centurion')">Book with Blessing</button>
                </div>

                <!-- Profile 4 -->
                <div class="profile-card">
                    <div class="profile-header">
                        <div class="profile-avatar">DV</div>
                        <div class="profile-meta">
                            <h4>David van der Merwe</h4>
                            <p>Cape Town Metro &bull; Painter</p>
                            <span class="verified-badge">&#10003; Master Painter &bull; 10 Yrs Exp</span>
                        </div>
                    </div>
                    <div class="status-container">
                        <div class="status-pill">
                            <span class="dot-booked"></span>
                            <span class="text-booked">Booked until Tomorrow</span>
                        </div>
                        <strong>R65 / hr</strong>
                    </div>
                    <button type="button" class="btn-action" onclick="bookPro('David van der Merwe', 'Painter', 'Cape Town Metro')">Book with David</button>
                </div>
            </div>
        </section>

        <!-- VIEW 4: INTAKE FORMS SCREEN -->
        <section id="view-booking" class="view-section">
            <div class="form-panel">
                <div class="section-header">
                    <h2>Book Verified Local Help</h2>
                    <p>Nationwide on-demand booking intake. Fast dispatch with escrow guarantee.</p>
                </div>

                <form id="bookingForm" action="YOUR_WEBHOOK_URL_HERE" method="POST" onsubmit="handleFormSubmit(event)">
                    <div class="form-group">
                        <label for="client_name">Your Name &amp; Surname *</label>
                        <input type="text" id="client_name" name="client_name" placeholder="e.g. Sipho Sithole" required>
                    </div>

                    <div class="form-group">
                        <label for="client_phone">Mobile Phone Number *</label>
                        <input type="tel" id="client_phone" name="client_phone" placeholder="082 123 4567" required>
                    </div>

                    <div class="form-group">
                        <label for="client_area">Select Your Area *</label>
                        <select id="client_area" name="client_area" required>
                            <option value="">-- Select Your Area --</option>
                            <optgroup label="Gauteng">
                                <option value="East Rand">East Rand (Springs, Benoni, Boksburg)</option>
                                <option value="Johannesburg North">Johannesburg North (Sandton, Randburg)</option>
                                <option value="Pretoria &amp; Centurion">Pretoria &amp; Centurion</option>
                                <option value="JHB Central &amp; South">JHB Central &amp; South</option>
                                <option value="West Rand">West Rand (Roodepoort, Krugersdorp)</option>
                            </optgroup>
                            <optgroup label="Western Cape">
                                <option value="Cape Town Metro">Cape Town Metro (City Bowl, Southern Suburbs)</option>
                                <option value="Cape Town Atlantic &amp; West Coast">Cape Town Atlantic &amp; West Coast</option>
                            </optgroup>
                            <optgroup label="KwaZulu-Natal">
                                <option value="Durban Metro">Durban Metro (Central, Berea, Bluff)</option>
                                <option value="Durban North &amp; Umhlanga">Durban North &amp; Umhlanga</option>
                            </optgroup>
                            <optgroup label="Other Regional Hubs">
                                <option value="Gqeberha">Gqeberha / Port Elizabeth</option>
                                <option value="Bloemfontein">Bloemfontein Metro</option>
                            </optgroup>
                        </select>
                        <input type="hidden" id="client_suburb" name="client_suburb" value="">
                    </div>

                    <div class="form-group">
                        <label for="service_type">Service Required *</label>
                        <select id="service_type" name="service_type" required>
                            <option value="">-- Select Service --</option>
                            <option value="Domestic Cleaner">Domestic Cleaner (R50 / hr &bull; Min 4 hrs)</option>
                            <option value="Gardener">Gardener (R50 / hr &bull; Min 4 hrs)</option>
                            <option value="Painter">Painter (R65 / hr &bull; Min 4 hrs)</option>
                            <option value="Tiler">Tiler (R65 / hr &bull; Min 4 hrs)</option>
                            <option value="Plumber / Artisan">Plumber or Electrician (R450 Call-out)</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="booking_date">Requested Service Date *</label>
                        <input type="date" id="booking_date" name="booking_date" required>
                    </div>

                    <div class="form-group">
                        <label for="job_notes">Job Notes / Requests</label>
                        <textarea id="job_notes" name="job_notes" rows="3" placeholder="Special requirements, address details, or gate instructions..."></textarea>
                    </div>

                    <div class="escrow-card">
                        &#128274; <strong>Secured Escrow Payment:</strong> Use Mobile Number as reference. Pay to Capitec. Funds released only upon job completion.
                    </div>

                    <div class="legal-check">
                        <input type="checkbox" id="liability" required>
                        <label for="liability">I agree BookaService holds no liability for theft or property damage.</label>
                    </div>

                    <button type="submit" class="btn-action">Submit Secure Booking Request</button>
                </form>
            </div>
        </section>
    </main>

    <!-- FOOTER EXTRACTION DRAWER -->
    <footer>
        <div class="accordion-trigger" onclick="toggleAccordion()">
            &#128737; Area Service Guarantee &amp; Escrow Policy &#9660;
        </div>
        <div class="accordion-details" id="accordionContent">
            All service professionals undergo criminal background vetting and police record clearance. Clients deposit funds into Capitec Escrow; payments are released only after satisfactory service verification. Regional hubs serviced: East Rand, Johannesburg North, Pretoria &amp; Centurion, JHB Central &amp; South, West Rand, Cape Town Metro, and Durban Metro. BookaService holds no liability for theft or property damage.
        </div>
    </footer>

    <script>
        let currentView = 'landing';

        function showView(viewName) {
            currentView = viewName;
            document.querySelectorAll('.view-section').forEach(sec => sec.classList.remove('active'));
            const target = document.getElementById('view-' + viewName);
            if (target) target.classList.add('active');

            const backBtn = document.getElementById('backBtn');
            if (viewName === 'landing') {
                backBtn.style.display = 'none';
            } else {
                backBtn.style.display = 'inline-block';
            }
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function goBack() {
            showView('landing');
        }

        function selectCategory(catName) {
            showView('booking');
            const select = document.getElementById('service_type');
            if (select) {
                for (let i = 0; i < select.options.length; i++) {
                    if (select.options[i].value === catName) {
                        select.selectedIndex = i;
                        break;
                    }
                }
            }
        }

        function bookPro(proName, serviceName, areaName) {
            showView('booking');
            const serviceSelect = document.getElementById('service_type');
            if (serviceSelect) {
                for (let i = 0; i < serviceSelect.options.length; i++) {
                    if (serviceSelect.options[i].value === serviceName) {
                        serviceSelect.selectedIndex = i;
                        break;
                    }
                }
            }
            const areaSelect = document.getElementById('client_area');
            if (areaSelect) {
                for (let i = 0; i < areaSelect.options.length; i++) {
                    if (areaSelect.options[i].value === areaName) {
                        areaSelect.selectedIndex = i;
                        break;
                    }
                }
            }
            const notes = document.getElementById('job_notes');
            if (notes) {
                notes.value = 'Requested pro: ' + proName;
            }
        }

        function toggleAccordion() {
            const drawer = document.getElementById('accordionContent');
            if (drawer.style.display === 'block') {
                drawer.style.display = 'none';
            } else {
                drawer.style.display = 'block';
            }
        }

        function handleFormSubmit(e) {
            e.preventDefault();
            const name = document.getElementById('client_name').value;
            const phone = document.getElementById('client_phone').value;
            const area = document.getElementById('client_area').value;
            const service = document.getElementById('service_type').value;
            const date = document.getElementById('booking_date').value;
            const areaCode = area ? area.replace(/[^a-zA-Z]/g, '').substring(0,3).toUpperCase() : 'ZAF';
            const ref = 'BKS-' + areaCode + '-' + Math.floor(1000 + Math.random() * 9000);

            alert('Booking Request Secured!\n\n' +
                  'Reference: ' + ref + '\n' +
                  'Client: ' + name + '\n' +
                  'Service: ' + service + '\n' +
                  'Area: ' + area + '\n' +
                  'Date: ' + date + '\n\n' +
                  'Capitec Escrow Reference: ' + phone);
        }

        // Set today as default min date
        const today = new Date().toISOString().split('T')[0];
        const dateInput = document.getElementById('booking_date');
        if (dateInput) {
            dateInput.min = today;
            dateInput.value = today;
        }
    </script>
</body>
</html>
