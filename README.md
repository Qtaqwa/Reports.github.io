# قافلة التقوى
# مع التقوى .. للحج معنى آخر

<h1>بيانات الحجاج</h1>
<table id="data-table">
  <thead>
    <tr id="table-header"></tr>
  </thead>
  <tbody id="table-body"></tbody>
</table>

<script>
  // Fetch CSV data from GitHub raw link
  async function fetchData() {
    const csvUrl = 'YOUR_CSV_RAW_LINK';
    const response = await fetch(csvUrl);
    const csvText = await response.text();
    const rows = csvText.split('\n').map(row => row.split(','));

    // Render table headers
    const headerRow = rows[0];
    const headerHtml = headerRow.map(header => `<th>${header}</th>`).join('');
    document.getElementById('table-header').innerHTML = headerHtml;

    // Render table rows
    const bodyHtml = rows.slice(1).map(row => `
      <tr>${row.map(cell => `<td>${cell}</td>`).join('')}</tr>
    `).join('');
    document.getElementById('table-body').innerHTML = bodyHtml;
  }

  // Initialize
  fetchData();
</script>
