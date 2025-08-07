<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Amazon Barcode Generator</title>
    <script src="https://cdn.jsdelivr.net/npm/jsbarcode@3.11.5/dist/JsBarcode.all.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
    <style>
        @page {
            size: A4;
            margin: 0;
        }
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f5f5f5;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        .controls {
            background: #f1f3f4;
            padding: 15px;
            border-radius: 5px;
            margin-bottom: 20px;
        }
        .form-group {
            margin-bottom: 15px;
        }
        label {
            display: block;
            font-weight: bold;
            margin-bottom: 5px;
        }
        input, textarea {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }
        button {
            padding: 10px 15px;
            background: #FF9900;
            border: none;
            color: white;
            cursor: pointer;
            border-radius: 4px;
            font-weight: bold;
            margin-right: 10px;
        }
        .barcode-sheet {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 0;
            width: 210mm;
            min-height: 297mm;
            margin: 0 auto;
            padding: 0;
        }
        .barcode-item {
            width: 63mm;
            height: 33mm;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 2mm;
            box-sizing: border-box;
            position: relative;
            border: 1px dotted #ccc;
        }
        .barcode-svg {
            width: 60mm;
            height: 15mm;
            margin: 1mm 0;
        }
        .barcode-number {
            font-size: 3.5mm;
            font-family: Arial, sans-serif;
            margin: 1mm 0;
            text-align: center;
            word-break: break-all;
        }
        .product-name {
            font-size: 3mm;
            margin: 1mm 0;
            text-align: center;
            line-height: 1.2;
            max-width: 100%;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        
        @media print {
            body {
                padding: 0;
                background: none;
            }
            .container {
                box-shadow: none;
                padding: 0;
            }
            .controls {
                display: none;
            }
            .barcode-sheet {
                gap: 0;
            }
            .barcode-item {
                border: none;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 style="color: #FF9900; text-align: center;">Amazon Barcode Generator</h1>
        
        <div class="controls">
            <div class="form-group">
                <label for="uploadExcel">Upload Excel File:</label>
                <input type="file" id="uploadExcel" accept=".xlsx,.xls">
                <small>Format: Column A = Barcode, Column B = Product Name, Column C = Quantity</small>
            </div>
            
            <div style="display: flex; gap: 15px;">
                <div style="flex: 1;">
                    <div class="form-group">
                        <label for="barcodeText">Barcode:</label>
                        <input type="text" id="barcodeText" value="X0028MTWPZ">
                    </div>
                </div>
                <div style="flex: 2;">
                    <div class="form-group">
                        <label for="productName">Product Name:</label>
                        <input type="text" id="productName" value="Scalpe Pro Anti-dandruff Shampoo 100ml">
                    </div>
                </div>
                <div style="flex: 1;">
                    <div class="form-group">
                        <label for="barcodeQty">Quantity:</label>
                        <input type="number" id="barcodeQty" value="27" min="1">
                    </div>
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 15px;">
                <button onclick="generateBarcodes()">Generate Barcodes</button>
                <button onclick="downloadSample()">Download Sample Excel</button>
                <button onclick="window.print()">Print Barcodes</button>
            </div>
        </div>
        
        <div class="barcode-sheet" id="barcodeSheet">
            <!-- Barcodes will appear here -->
        </div>
    </div>

    <script>
        let barcodeData = [];
        
        function generateBarcodes() {
            const sheet = document.getElementById('barcodeSheet');
            sheet.innerHTML = '';
            
            if (barcodeData.length === 0) {
                // Generate from form inputs
                const barcodeText = document.getElementById('barcodeText').value.trim();
                const productName = document.getElementById('productName').value.trim();
                const qty = parseInt(document.getElementById('barcodeQty').value) || 1;
                
                if (!barcodeText) {
                    alert("Please enter a valid barcode");
                    return;
                }
                
                for (let i = 0; i < qty; i++) {
                    barcodeData.push({
                        barcode: barcodeText,
                        name: productName
                    });
                }
            }
            
            // Generate all barcodes (quantity is handled but not displayed)
            barcodeData.forEach((item, index) => {
                const barcodeItem = document.createElement('div');
                barcodeItem.className = 'barcode-item';
                
                const svg = document.createElementNS('http://www.w3.org/2000/svg', 'svg');
                svg.className = 'barcode-svg';
                svg.id = 'barcode-' + index;
                
                const numberDiv = document.createElement('div');
                numberDiv.className = 'barcode-number';
                numberDiv.textContent = item.barcode;
                
                const nameDiv = document.createElement('div');
                nameDiv.className = 'product-name';
                nameDiv.textContent = item.name;
                
                barcodeItem.appendChild(svg);
                barcodeItem.appendChild(numberDiv);
                barcodeItem.appendChild(nameDiv);
                sheet.appendChild(barcodeItem);
                
                // Generate barcode with perfect Amazon sizing
                JsBarcode(svg, item.barcode, {
                    format: "CODE128",
                    lineColor: "#000000",
                    width: 1.2,
                    height: 15,
                    displayValue: false,
                    margin: 5,
                    flat: true
                });
            });
        }
        
        function downloadSample() {
            const sampleData = [
                ["Barcode", "Product Name", "Quantity"],
                ["X0028MTWPZ", "Scalpe Pro Anti-dandruff Shampoo 100ml", 10],
                ["X0029MTWPZ", "Scalpe Pro Conditioner 200ml", 5],
                ["X0030MTWPZ", "Scalpe Pro Hair Oil 50ml", 15]
            ];
            
            const wb = XLSX.utils.book_new();
            const ws = XLSX.utils.aoa_to_sheet(sampleData);
            XLSX.utils.book_append_sheet(wb, ws, "Barcode Data");
            XLSX.writeFile(wb, "Amazon_Barcode_Sample.xlsx");
        }
        
        function handleFileUpload(e) {
            const file = e.target.files[0];
            const reader = new FileReader();
            
            reader.onload = function(e) {
                const data = new Uint8Array(e.target.result);
                const workbook = XLSX.read(data, { type: 'array' });
                const firstSheet = workbook.Sheets[workbook.SheetNames[0]];
                const jsonData = XLSX.utils.sheet_to_json(firstSheet, { header: 1 });
                
                barcodeData = [];
                
                // Process Excel data (skip header row)
                for (let i = 1; i < jsonData.length; i++) {
                    const row = jsonData[i];
                    if (row && row[0]) {
                        const qty = parseInt(row[2]) || 1;
                        for (let j = 0; j < qty; j++) {
                            barcodeData.push({
                                barcode: String(row[0]).trim(),
                                name: row[1] ? String(row[1]).trim() : "Amazon Product"
                            });
                        }
                    }
                }
                
                if (barcodeData.length > 0) {
                    generateBarcodes();
                } else {
                    alert("No valid barcode data found in Excel file");
                }
            };
            
            reader.readAsArrayBuffer(file);
        }
        
        // Initialize
        document.getElementById('uploadExcel').addEventListener('change', handleFileUpload);
        window.addEventListener('load', generateBarcodes);
    </script>
</body>
</html>
