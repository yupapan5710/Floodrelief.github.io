# Floodrelief.github.io

<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <title>ศูนย์กลางแจ้งขอความช่วยเหลือ น้ำท่วมภาคใต้</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <!-- ใช้ Bootstrap จาก CDN เพื่อให้สวยขึ้นหน่อย -->
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
  />
</head>
<body class="bg-light">
  <nav class="navbar navbar-expand-lg navbar-dark bg-primary mb-4">
    <div class="container-fluid">
      <span class="navbar-brand">
        ศูนย์แจ้งขอความช่วยเหลือ น้ำท่วมภาคใต้
      </span>
    </div>
  </nav>

  <div class="container mb-5">
    <div class="row">
      <!-- ฟอร์มแจ้งขอความช่วยเหลือ -->
      <div class="col-lg-5 mb-4">
        <div class="card shadow-sm">
          <div class="card-header bg-danger text-white">
            แจ้งขอความช่วยเหลือ
          </div>
          <div class="card-body">
            <form id="helpForm">
              <div class="mb-2">
                <label class="form-label">ชื่อผู้แจ้ง</label>
                <input type="text" class="form-control" id="reporterName" required />
              </div>

              <div class="mb-2">
                <label class="form-label">เบอร์ติดต่อกลับ</label>
                <input type="tel" class="form-control" id="phone" required />
              </div>

              <div class="mb-2">
                <label class="form-label">จังหวัด / อำเภอ / ตำบล</label>
                <input type="text" class="form-control" id="area" placeholder="เช่น ต.บางแก้ว อ.หาดใหญ่ จ.สงขลา" required />
              </div>

              <div class="mb-2">
                <label class="form-label">รายละเอียดที่อยู่ / พิกัดบ้าน</label>
                <textarea class="form-control" id="address" rows="2" required></textarea>
              </div>

              <div class="mb-2">
                <label class="form-label">ลิงก์พิกัดแผนที่ (Google Maps) หรือ ละติจูด,ลองจิจูด</label>
                <input type="text" class="form-control" id="locationLink" placeholder="วางลิงก์ Google Maps หรือพิกัด"/>
              </div>

              <hr />

              <div class="mb-2">
                <label class="form-label">จำนวนคนในบ้าน</label>
                <div class="row g-2">
                  <div class="col-6">
                    <label class="form-label small">เด็ก</label>
                    <input type="number" min="0" value="0" class="form-control" id="children" />
                  </div>
                  <div class="col-6">
                    <label class="form-label small">ผู้ใหญ่</label>
                    <input type="number" min="0" value="0" class="form-control" id="adults" />
                  </div>
                  <div class="col-6">
                    <label class="form-label small">ผู้สูงอายุ</label>
                    <input type="number" min="0" value="0" class="form-control" id="elderly" />
                  </div>
                  <div class="col-6">
                    <label class="form-label small">ผู้ป่วย / ผู้พิการ</label>
                    <input type="number" min="0" value="0" class="form-control" id="patients" />
                  </div>
                  <div class="col-6">
                    <label class="form-label small">สัตว์เลี้ยง</label>
                    <input type="number" min="0" value="0" class="form-control" id="pets" />
                  </div>
                </div>
              </div>

              <div class="mb-2">
                <label class="form-label">ระดับน้ำท่วม</label>
                <select class="form-select" id="waterLevel">
                  <option value="ไม่ทราบ">ไม่ทราบ / ไม่ระบุ</option>
                  <option value="ระดับเข่า">ระดับเข่า</option>
                  <option value="ระดับเอว">ระดับเอว</option>
                  <option value="ระดับอก">ระดับอก</option>
                  <option value="สูงกว่าหน้าต่าง">สูงกว่าหน้าต่าง</option>
                </select>
              </div>

              <div class="mb-2">
                <label class="form-label">ความช่วยเหลือที่ต้องการ (เลือกได้หลายข้อ)</label>
                <div class="form-check">
                  <input class="form-check-input" type="checkbox" value="อาหารแห้ง" id="needFood">
                  <label class="form-check-label" for="needFood">อาหารแห้ง/อาหารพร้อมทาน</label>
                </div>
                <div class="form-check">
                  <input class="form-check-input" type="checkbox" value="น้ำดื่ม" id="needWater">
                  <label class="form-check-label" for="needWater">น้ำดื่ม</label>
                </div>
                <div class="form-check">
                  <input class="form-check-input" type="checkbox" value="ยาและเวชภัณฑ์" id="needMedicine">
                  <label class="form-check-label" for="needMedicine">ยาและเวชภัณฑ์</label>
                </div>
                <div class="form-check">
                  <input class="form-check-input" type="checkbox" value="เรือ / พาหนะช่วยเหลือ" id="needBoat">
                  <label class="form-check-label" for="needBoat">เรือ / พาหนะช่วยเหลือ</label>
                </div>
                <div class="form-check">
                  <input class="form-check-input" type="checkbox" value="อพยพออกจากพื้นที่" id="needEvac">
                  <label class="form-check-label" for="needEvac">อพยพออกจากพื้นที่</label>
                </div>
              </div>

              <div class="mb-3">
                <label class="form-label">รายละเอียดเพิ่มเติม</label>
                <textarea class="form-control" id="detail" rows="2" placeholder="เช่น ผู้ป่วยติดเตียง 1 คน น้ำท่วมเข้าบ้านแล้ว รถเข้าไม่ถึง"></textarea>
              </div>

              <button type="submit" class="btn btn-danger w-100">
                ส่งคำขอความช่วยเหลือ
              </button>
            </form>
          </div>
        </div>
      </div>

      <!-- รายการคำขอความช่วยเหลือ -->
      <div class="col-lg-7 mb-4">
        <div class="card shadow-sm">
          <div class="card-header bg-success text-white d-flex justify-content-between align-items-center">
            <span>รายการขอความช่วยเหลือ</span>
            <select id="statusFilter" class="form-select form-select-sm" style="width:auto;">
              <option value="all">แสดงทั้งหมด</option>
              <option value="pending">เฉพาะรอความช่วยเหลือ</option>
              <option value="done">เฉพาะได้รับความช่วยเหลือแล้ว</option>
            </select>
          </div>
          <div class="card-body">
            <div id="requestsList" class="small">
              <!-- รายการจะถูก generate ด้วย JavaScript -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <script>
    // เก็บข้อมูลใน localStorage เพื่อให้รีเฟรชแล้วยังอยู่ (ต้นแบบ)
    const STORAGE_KEY = "flood_help_requests";

    function loadRequests() {
      const data = localStorage.getItem(STORAGE_KEY);
      return data ? JSON.parse(data) : [];
    }

    function saveRequests(requests) {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(requests));
    }

    function renderRequests() {
      const container = document.getElementById("requestsList");
      const requests = loadRequests();
      const filter = document.getElementById("statusFilter").value;

      container.innerHTML = "";

      const filtered = requests.filter(r => {
        if (filter === "pending") return r.status === "รอความช่วยเหลือ";
        if (filter === "done") return r.status === "ได้รับความช่วยเหลือแล้ว";
        return true;
      });

      if (filtered.length === 0) {
        container.innerHTML = "<p class='text-muted'>ยังไม่มีรายการ หรือไม่พบข้อมูลตามตัวกรอง</p>";
        return;
      }

      filtered.forEach((r, index) => {
        const totalPeople =
          r.children + r.adults + r.elderly + r.patients;

        const statusBadge =
          r.status === "รอความช่วยเหลือ"
            ? "<span class='badge bg-danger'>รอความช่วยเหลือ</span>"
            : "<span class='badge bg-success'>ได้รับความช่วยเหลือแล้ว</span>";

        const card = document.createElement("div");
        card.className = "border rounded p-2 mb-2";

        card.innerHTML = `
          <div class="d-flex justify-content-between">
            <div>
              <strong>${statusBadge} พื้นที่: ${r.area}</strong><br/>
              ผู้แจ้ง: ${r.reporterName} | โทร: ${r.phone}<br/>
              คนในบ้านรวม ~ <strong>${totalPeople}</strong> คน
              (${r.children} เด็ก, ${r.adults} ผู้ใหญ่, ${r.elderly} ผู้สูงอายุ, ${r.patients} ผู้ป่วย)
            </div>
            <div class="text-end">
              <button class="btn btn-sm btn-outline-secondary mb-1" onclick="toggleStatus(${r.id})">
                เปลี่ยนสถานะ
              </button><br/>
              <button class="btn btn-sm btn-outline-primary" onclick="showDetail(${r.id})">
                รายละเอียด
              </button>
            </div>
          </div>
        `;

        container.appendChild(card);
      });
    }

    function toggleStatus(id) {
      const requests = loadRequests();
      const idx = requests.findIndex(r => r.id === id);
      if (idx === -1) return;

      requests[idx].status =
        requests[idx].status === "รอความช่วยเหลือ"
          ? "ได้รับความช่วยเหลือแล้ว"
          : "รอความช่วยเหลือ";

      saveRequests(requests);
      renderRequests();
    }

    function showDetail(id) {
      const requests = loadRequests();
      const r = requests.find(x => x.id === id);
      if (!r) return;

      const needsText = r.needs.length > 0 ? r.needs.join(", ") : "ไม่ระบุ";

      alert(
        [
          `สถานะ: ${r.status}`,
          `ผู้แจ้ง: ${r.reporterName}`,
          `เบอร์ติดต่อ: ${r.phone}`,
          `พื้นที่: ${r.area}`,
          `ที่อยู่/พิกัด: ${r.address}`,
          r.locationLink ? `ลิงก์แผนที่: ${r.locationLink}` : "",
          `ระดับน้ำท่วม: ${r.waterLevel}`,
          `เด็ก: ${r.children}, ผู้ใหญ่: ${r.adults}, ผู้สูงอายุ: ${r.elderly}, ผู้ป่วย: ${r.patients}, สัตว์เลี้ยง: ${r.pets}`,
          `ความต้องการ: ${needsText}`,
          `รายละเอียดเพิ่มเติม: ${r.detail || "-"}`
        ].filter(Boolean).join("\n")
      );
    }

    // ส่งฟอร์ม
    document.getElementById("helpForm").addEventListener("submit", function (e) {
      e.preventDefault();

      const reporterName = document.getElementById("reporterName").value.trim();
      const phone = document.getElementById("phone").value.trim();
      const area = document.getElementById("area").value.trim();
      const address = document.getElementById("address").value.trim();
      const locationLink = document.getElementById("locationLink").value.trim();
      const children = parseInt(document.getElementById("children").value || "0");
      const adults = parseInt(document.getElementById("adults").value || "0");
      const elderly = parseInt(document.getElementById("elderly").value || "0");
      const patients = parseInt(document.getElementById("patients").value || "0");
      const pets = parseInt(document.getElementById("pets").value || "0");
      const waterLevel = document.getElementById("waterLevel").value;
      const detail = document.getElementById("detail").value.trim();

      const needs = [];
      if (document.getElementById("needFood").checked) needs.push("อาหารแห้ง/อาหารพร้อมทาน");
      if (document.getElementById("needWater").checked) needs.push("น้ำดื่ม");
      if (document.getElementById("needMedicine").checked) needs.push("ยาและเวชภัณฑ์");
      if (document.getElementById("needBoat").checked) needs.push("เรือ / พาหนะช่วยเหลือ");
      if (document.getElementById("needEvac").checked) needs.push("อพยพออกจากพื้นที่");

      const requests = loadRequests();
      const newId = requests.length ? Math.max(...requests.map(r => r.id)) + 1 : 1;

      const newRequest = {
        id: newId,
        reporterName,
        phone,
        area,
        address,
        locationLink,
        children,
        adults,
        elderly,
        patients,
        pets,
        waterLevel,
        needs,
        detail,
        status: "รอความช่วยเหลือ",
        createdAt: new Date().toISOString()
      };

      requests.push(newRequest);
      saveRequests(requests);

      alert("บันทึกคำขอความช่วยเหลือเรียบร้อยแล้ว ขอบคุณค่ะ");
      e.target.reset();
      renderRequests();
    });

    document.getElementById("statusFilter").addEventListener("change", renderRequests);

    // load initial
    renderRequests();
  </script>
</body>
</html>
