# steet js 사용해서 엑셀파일 불러오는방법

```html
<script src="https://unpkg.com/xlsx/dist/xlsx.full.min.js"></script>
```

```javascript
async function fetchExcelToJson(url) {
    try {
        const response = await fetch(url);
        const data = await response.arrayBuffer();
        const workbook = XLSX.read(new Uint8Array(data), { type: 'array' });
        const sheetName = workbook.SheetNames[0];
        const sheetData = XLSX.utils.sheet_to_json(workbook.Sheets[sheetName]);

        return sheetData;

    } catch (error) {
        console.error('엑셀 파일 가져오기 실패', error);
    }
};

fetchExcelToJson('../loc-chart.xlsx').then(data => {}) // 비동기임
```
