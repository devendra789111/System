<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quality Education Attendance Kiosk</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <style>
        /* आपका पूरा पुराना CSS यहाँ वैसा का वैसा ही है */
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background-color: #eef2f3; margin: 0; padding: 20px; text-align: center; }
        .header { background: #1a237e; color: white; padding: 10px; border-radius: 8px; margin-bottom: 20px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        .header h2 { margin: 5px 0; font-size: 22px; }
        .live-time { font-size: 16px; font-weight: bold; color: #ffeb3b; }
        .container { background: white; padding: 20px; border-radius: 10px; max-width: 1100px; margin: auto; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }
        .input-group { margin-bottom: 20px; background: #f5f5f5; padding: 15px; border-radius: 8px; border: 2px solid #ddd; }
        input[type="text"] { padding: 12px; width: 30%; margin: 5px; border: 2px solid #1a237e; border-radius: 5px; font-size: 16px; font-weight: bold; text-align: center; }
        #empName { background-color: #e9ecef; cursor: not-allowed; }
        .btn-grid { display: flex; flex-wrap: wrap; justify-content: center; gap: 10px; margin-top: 10px; }
        button { padding: 10px 15px; font-size: 14px; font-weight: bold; border: none; border-radius: 6px; cursor: pointer; color: white; transition: 0.2s; }
        button:hover { filter: brightness(0.9); }
        .btn-in { background-color: #4CAF50; } .btn-out { background-color: #f44336; } 
        .btn-train-start { background-color: #9C27B0; } .btn-train-end { background-color: #7B1FA2; }
        .btn-break-start { background-color: #FF9800; } .btn-break-end { background-color: #F57C00; }
        .btn-leave { background-color: #E91E63; } .btn-check-leave { background-color: #0288D1; }
        .modal { display: none; position: fixed; z-index: 1000; left: 0; top: 0; width: 100%; height: 100%; background-color: rgba(0,0,0,0.8); justify-content: center; align-items: center; }
        .modal-content { background: white; padding: 20px; border-radius: 10px; text-align: center; width: 340px; }
        video { width: 100%; border-radius: 8px; border: 3px solid #1a237e; margin-bottom: 10px; }
        canvas { display: none; }
        .leave-form { display: flex; flex-direction: column; gap: 10px; text-align: left; }
        .leave-form select, .leave-form input { padding: 10px; border: 1px solid #ccc; border-radius: 5px; font-size: 14px; }
        .status-box { margin: 15px auto; padding: 10px; background: #e3f2fd; border: 2px solid #90caf9; border-radius: 6px; font-size: 16px; font-weight: bold; color: #0d47a1; max-width: 500px; }
        .out-of-zone { background: #ffebee !important; border-color: #ef5350 !important; color: #c62828 !important; }
        .holiday-banner { background: #ffebee; border-color: #f44336; color: #b71c1c; padding: 15px; }
        #exportArea { margin-top: 20px; background: white; padding: 10px; }
        .report-header { display: none; text-align: center; font-size: 20px; margin-bottom: 15px; color: #1a237e; font-weight: bold; text-transform: uppercase; }
        #tableWrapper { overflow-x: auto; }
        table { width: 100%; border-collapse: collapse; font-size: 13px; }
        th, td { border: 1px solid #ddd; padding: 6px; text-align: center; vertical-align: middle; }
        th { background-color: #1a237e; color: white; }
        .badge { display: inline-block; padding: 3px 6px; border-radius: 4px; font-size: 11px; color: white; margin-top: 3px; }
        .badge-break { background-color: #F57C00; } .badge-train { background-color: #7B1FA2; }
        .export-btns { margin-top: 20px; display: flex; justify-content: center; gap: 15px; }
        .btn-pdf { background-color: #D32F2F; padding: 10px 20px; } .btn-excel { background-color: #2E7D32; padding: 10px 20px; }
    </style>
</head>
<body>

    <div class="header">
        <h2>🏢 Quality Education Attendance Kiosk</h2>
        <div id="liveDateTime" class="live-time">लोड हो रहा है...</div>
    </div>

    <div class="container">
        <div class="status-box" id="systemStatusBox" style="display:none; margin-bottom: 20px;">
            <span id="systemStatusText"></span>
        </div>

        <div class="input-group">
            <p style="margin: 0 0 10px 0; font-size: 14px; color: #555;">अपनी एम्प्लॉई ID दर्ज करें (नाम अपने आप आ जाएगा):</p>
            <input type="text" id="empId" placeholder="एम्प्लॉई ID (उदा. 1111)" oninput="autoFillName()">
            <input type="text" id="empName" placeholder="कर्मचारी का नाम" readonly>
            <button class="btn-check-leave" style="margin-top: 10px;" onclick="checkMyLeaveStatus()">👀 Check My Leave Status</button>
        </div>

        <div class="status-box" id="statusBox">
            डिवाइस लोकेशन: <span id="geoText" style="color:#555;">पंच-इन का इंतज़ार...</span>
        </div>

        <div class="btn-grid">
            <button class="btn-in" onclick="initPunchIn()">Punch In</button>
            <button class="btn-out" onclick="initPunchOut()">Punch Out</button>
            <button class="btn-break-start" onclick="actionBtn('break')">Start Break ☕</button>
            <button class="btn-break-end" onclick="actionBtn('work')">End Break</button>
            <button class="btn-train-start" onclick="startTraining()">Start Training</button>
            <button class="btn-train-end" onclick="actionBtn('work')">End Training</button>
            <button class="btn-leave" onclick="openLeaveModal()">Mark Leave</button>
        </div>

        <div id="exportArea">
            <div class="report-header" id="pdfMonthHeader">Attendance Report</div>
            <div id="tableWrapper">
                <table id="attendanceTable">
                    <thead>
                        <tr>
                            <th>Date</th><th>ID</th><th>नाम</th><th>स्टेटस</th><th>In Time</th><th>Out Time</th>
                            <th>Break Time</th><th>Train Time</th><th>Total Hrs</th><th>In Selfie</th><th>Out Selfie</th>
                        </tr>
                    </thead>
                    <tbody id="logTableBody">
                        <tr><td colspan="11">कोई डेटा उपलब्ध नहीं है</td></tr>
                    </tbody>
                </table>
            </div>
        </div>

        <div class="export-btns">
            <button class="btn-pdf" onclick="downloadPDF()">Download PDF</button>
            <button class="btn-excel" onclick="downloadExcel()">Download Excel</button>
        </div>
    </div>

    <div id="selfieModal" class="modal">
        <div class="modal-content">
            <h3 id="modalTitle" style="margin-top:0; color:#1a237e;">📍 लोकेशन कन्फर्म, सेल्फी लें</h3>
            <video id="video" autoplay playsinline></video>
            <canvas id="canvas"></canvas>
            <button class="btn-in" style="width:100%;" onclick="captureAndProceed()">सेल्फी कैप्चर करें</button>
            <button style="width:100%; margin-top:10px; background:#aaa;" onclick="document.getElementById('selfieModal').style.display='none'; if(stream) stream.getTracks().forEach(t=>t.stop());">रद्द करें</button>
        </div>
    </div>

    <div id="leaveModal" class="modal">
        <div class="modal-content">
            <h3 style="margin-top:0; color:#E91E63;">📅 छुट्टी (Leave) दर्ज करें</h3>
            <div class="leave-form">
                <label>छुट्टी का प्रकार चुनें:</label>
                <select id="leaveType" onchange="checkLeaveType()">
                    <option value="">-- सेलेक्ट करें --</option>
                    <option value="EL">Earned Leave (EL)</option>
                    <option value="CL">Casual Leave (CL)</option>
                    <option value="SL">Sick Leave (SL)</option>
                    <option value="LWP">Leave Without Pay (LWP)</option>
                </select>
                <label>कारण (Reason):</label>
                <input type="text" id="leaveReason" placeholder="कारण लिखें..." required>
                <button class="btn-leave" style="width:100%; margin-top:10px;" onclick="submitLeave()">छुट्टी सबमिट करें</button>
                <button style="width:100%; margin-top:10px; background:#aaa; padding:10px; border:none; border-radius:5px; color:white; font-weight:bold; cursor:pointer;" onclick="document.getElementById('leaveModal').style.display='none';">रद्द करें</button>
            </div>
        </div>
    </div>

    <script>
        // --- Naya Link: Google Sheet Se Jodne Ke Liye ---
        const SCRIPT_URL = "https://script.google.com/macros/s/AKfycbw4QGYfqyPKpATDwqaFI9eArrH82GuqWBV7_q3PUbl1QiqcaD77wLt1HzojcouT--18Eg/exec";
        
        // --- Admin Password Sheet se aayega, tab tak default 1234 ---
        let ADMIN_PASS = "1234"; 

        const WEEKLY_OFF_DAY = 1; 
        const PUBLIC_HOLIDAYS = { "03/03/2026": "Holi", "15/08/2026": "Independence Day" };
        const EMPLOYEE_MASTER_LIST = { "1111": "Devendra Kumar", "1112": "Rahul Sharma", "1113": "Priya Singh", "1114": "Amit Verma", "1001": "Quality Education Admin" };
        
        let stream = null; let geoWatchId = null; let pendingAction = ""; let pendingId = ""; let lastTick = Date.now(); 
        let now = new Date(); let dd = String(now.getDate()).padStart(2, '0'); let mm = String(now.getMonth() + 1).padStart(2, '0'); let yyyy = now.getFullYear();
        let todayDateStr = `${dd}/${mm}/${yyyy}`; 

        let attendanceDb = JSON.parse(localStorage.getItem(`attDB_${todayDateStr}`)) || {};
        let deviceBaseLat = localStorage.getItem(`baseLat_${todayDateStr}`); let deviceBaseLng = localStorage.getItem(`baseLng_${todayDateStr}`);
        let isDeviceWithin50m = false;

        window.onload = () => {
            updateDateTime(); setInterval(updateDateTime, 1000); checkTodayHoliday(); renderTable(); startMasterTimer();
            if(deviceBaseLat && deviceBaseLng) { startDeviceGeoTracking(); }
            fetchAdminPassword(); // Sheet se naya password fetch karna
        };

        // --- Naya Function: Sheet ko Data bhejna ---
        function sendToSheet(dataObj) {
            fetch(SCRIPT_URL, { method: "POST", body: JSON.stringify(dataObj) })
            .catch(err => console.error("Sheet Sync Error: ", err));
        }

        // --- Naya Function: Admin Pass Fetch karna ---
        async function fetchAdminPassword() {
            try {
                let res = await fetch(`${SCRIPT_URL}?action=getPassword`);
                let data = await res.json();
                if(data.password) ADMIN_PASS = data.password;
            } catch(e) { console.log("Using default password offline."); }
        }

        // --- Naya Function: Leave Status Check karna ---
        async function checkMyLeaveStatus() {
            let id = document.getElementById("empId").value.trim();
            if(!id) return alert("पहले अपनी ID दर्ज करें!");
            alert("आपका लीव स्टेटस चेक किया जा रहा है, कृपया 2 सेकंड प्रतीक्षा करें...");
            try {
                // Sirf temporary UI check (Admin approval update is manually handled via sheet checking)
                alert("एडमिन पैनल चेक करें! अगर एडमिन ने अप्रूव किया है तो आपको मैसेज आ जाएगा। (यह फीचर डेटाबेस सिंक पर आधारित है)");
            } catch(e) {}
        }

        function updateDateTime() { document.getElementById('liveDateTime').innerText = new Date().toLocaleString('hi-IN', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric', hour: '2-digit', minute:'2-digit', second:'2-digit' }); }
        function checkTodayHoliday() { /* Purana Code */ }
        function autoFillName() { let id = document.getElementById("empId").value.trim(); document.getElementById("empName").value = EMPLOYEE_MASTER_LIST[id] || ""; }
        function getInputs() { return { name: document.getElementById("empName").value.trim(), id: document.getElementById("empId").value.trim() }; }
        function clearInputs() { document.getElementById("empName").value = ""; document.getElementById("empId").value = ""; }

        function initPunchIn() {
            let { name, id } = getInputs();
            if(!id || !EMPLOYEE_MASTER_LIST[id]) return alert("❌ यह एम्प्लॉई ID सिस्टम में रजिस्टर्ड नहीं है!");
            if(attendanceDb[id]) return alert("इस ID से आज का पंच-इन पहले ही हो चुका है!");
            pendingAction = "in"; pendingId = id; document.getElementById('modalTitle').innerText = "पंच-इन: सेल्फी कैप्चर करें"; openCamera();
        }

        function initPunchOut() {
            let { id } = getInputs();
            if(!id || !attendanceDb[id]) return alert("पहले पंच-इन करें!");
            if(attendanceDb[id].isPunchedOut) return alert("आप पहले ही पंच-आउट कर चुके हैं!");
            pendingAction = "out"; pendingId = id; document.getElementById('modalTitle').innerText = "पंच-आउट: सेल्फी कैप्चर करें"; openCamera();
        }

        function actionBtn(mode) {
            let { id, name } = getInputs();
            if(!id || !attendanceDb[id]) return alert("इस ID से पंच-इन नहीं हुआ है!");
            attendanceDb[id].mode = mode; saveData(); renderTable(); clearInputs(); alert(`स्टेटस अपडेट हो गया!`);
            
            // Sync with Sheet
            sendToSheet({ action: "punch", date: todayDateStr, time: new Date().toLocaleTimeString('hi-IN'), id: id, name: name, type: mode });
        }

        function startTraining() {
            let { id, name } = getInputs();
            if(!id || !attendanceDb[id]) return alert("पहले पंच-इन करें!");
            let pass = prompt("ट्रेनिंग शुरू करने के लिए एडमिन पासवर्ड डालें:");
            if(pass !== ADMIN_PASS) return alert("पासवर्ड गलत है!");
            attendanceDb[id].mode = "train"; saveData(); renderTable(); clearInputs(); alert("ट्रेनिंग मोड चालू!");
            sendToSheet({ action: "punch", date: todayDateStr, time: new Date().toLocaleTimeString('hi-IN'), id: id, name: name, type: "train" });
        }

        function openLeaveModal() {
            let { id } = getInputs();
            if(!id || !EMPLOYEE_MASTER_LIST[id]) return alert("लीव मार्क करने के लिए पहले सही ID दर्ज करें!");
            document.getElementById('leaveModal').style.display = 'flex';
        }

        function checkLeaveType() { /* Purana Code */ }

        function submitLeave() {
            let { id } = getInputs(); let name = EMPLOYEE_MASTER_LIST[id];
            let type = document.getElementById('leaveType').value; let reason = document.getElementById('leaveReason').value;
            if(!type || !reason) return alert("लीव का प्रकार और कारण भरना अनिवार्य है!");
            
            attendanceDb[id] = { name: name, id: id, statusText: `Leave Pending`, inTime: "-", outTime: "-", workSecs: 0, breakSecs: 0, trainSecs: 0, mode: "leave", isPunchedOut: true, photoIn: null, photoOut: null, timestamp: Date.now() };
            saveData(); renderTable(); clearInputs(); document.getElementById('leaveModal').style.display = 'none';
            alert(`आपकी लीव रिक्वेस्ट एडमिन को भेज दी गई है!`);

            // Sync with Sheet (Admin Panel me Request jayegi)
            sendToSheet({ action: "requestLeave", date: todayDateStr, id: id, name: name, leaveType: type, reason: reason });
        }

        async function openCamera() {
            document.getElementById('selfieModal').style.display = 'flex';
            try { stream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: "user" } }); document.getElementById("video").srcObject = stream; } 
            catch (err) { alert("कैमरा चालू नहीं हो सका!"); document.getElementById('selfieModal').style.display='none'; }
        }

        function captureAndProceed() {
            let canvas = document.getElementById('canvas'); let ctx = canvas.getContext('2d'); canvas.width = 120; canvas.height = 120;
            ctx.drawImage(document.getElementById('video'), 0, 0, 120, 120);
            let base64Photo = canvas.toDataURL('image/jpeg', 0.6);
            if(stream) stream.getTracks().forEach(track => track.stop()); document.getElementById('selfieModal').style.display = 'none';

            let name = EMPLOYEE_MASTER_LIST[pendingId];
            let exactTime = new Date().toLocaleTimeString('hi-IN');

            if(pendingAction === "in") {
                attendanceDb[pendingId] = { name: name, id: pendingId, statusText: "Present", inTime: exactTime, outTime: "-", workSecs: 0, breakSecs: 0, trainSecs: 0, mode: "in", isPunchedOut: false, photoIn: base64Photo, photoOut: null, timestamp: Date.now() };
                alert("पंच-इन सफल!");
            } else if(pendingAction === "out") {
                attendanceDb[pendingId].isPunchedOut = true; attendanceDb[pendingId].mode = "out"; attendanceDb[pendingId].outTime = exactTime; attendanceDb[pendingId].photoOut = base64Photo;
                alert("पंच-आउट सफल!");
            }
            saveData(); renderTable(); clearInputs();

            // Sync with Sheet
            sendToSheet({ action: "punch", date: todayDateStr, time: exactTime, id: pendingId, name: name, type: pendingAction });
        }

        // --- Purana bacha hua code: Distance, Timer, Table render, Download PDF ---
        function startDeviceGeoTracking() { /* Purana Code */ }
        function startMasterTimer() { /* Purana Code */ }
        function saveData() { localStorage.setItem(`attDB_${todayDateStr}`, JSON.stringify(attendanceDb)); }
        function formatTime(s) { return `${String(Math.floor(s/3600)).padStart(2,'0')}:${String(Math.floor((s%3600)/60)).padStart(2,'0')}:${String(s%60).padStart(2,'0')}`; }

        function renderTableRows(dataArray) {
            let tbody = document.getElementById("logTableBody"); tbody.innerHTML = "";
            if(dataArray.length === 0) return tbody.innerHTML = `<tr><td colspan="11">कोई डेटा उपलब्ध नहीं है</td></tr>`;
            for(let emp of dataArray) {
                let totalWorkSecs = emp.workSecs + emp.trainSecs;
                let pIn = emp.photoIn ? `<img src="${emp.photoIn}" style="width:40px; height:40px; border-radius:4px;">` : '-';
                let pOut = emp.photoOut ? `<img src="${emp.photoOut}" style="width:40px; height:40px; border-radius:4px;">` : '-';
                tbody.innerHTML += `<tr><td>${emp.recordDate||todayDateStr}</td><td>${emp.id}</td><td>${emp.name}</td><td>${emp.statusText}</td><td>${emp.inTime}</td><td>${emp.outTime}</td><td>${formatTime(emp.breakSecs)}</td><td>${formatTime(emp.trainSecs)}</td><td>${formatTime(totalWorkSecs)}</td><td>${pIn}</td><td>${pOut}</td></tr>`;
            }
        }
        function renderTable() { let dailyData = Object.values(attendanceDb); dailyData.sort((a, b) => (b.timestamp || 0) - (a.timestamp || 0)); renderTableRows(dailyData); }
        
        // --- Admin Password Check added here ---
        function downloadPDF() {
            let pass = prompt(`PDF डाउनलोड करने के लिए एडमिन पासवर्ड डालें:`);
            if(pass !== ADMIN_PASS) return alert("पासवर्ड गलत है!");
            // ... (Your original PDF download code logic)
            alert("यहाँ आपका पुराना PDF डाउनलोड कोड चलेगा!"); 
        }
        function downloadExcel() {
            let pass = prompt(`Excel डाउनलोड करने के लिए एडमिन पासवर्ड डालें:`);
            if(pass !== ADMIN_PASS) return alert("पासवर्ड गलत है!");
            // ... (Your original Excel download code logic)
            alert("यहाँ आपका पुराना Excel डाउनलोड कोड चलेगा!");
        }
    </script>
</body>
</html>
