<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>供應商售價表</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        h1 {
            text-align: center;
            color: #333;
        }
        #search {
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
            font-size: 16px;
            box-sizing: border-box;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
            color: #333;
        }
        tr:nth-child(even) {
            background-color: #f9f9f9;
        }
        tr:hover {
            background-color: #f5f5f5;
        }
    </style>
</head>
<body>
    <h1>供應商售價表</h1>
    <p>Data Source: Excel 文件</p>
    <input type="text" id="search" placeholder="輸入搜尋關鍵字..." onkeyup="searchTable()">
    <table id="supplierTable">
        <thead>
            <tr>
                <th>供應商</th>
                <th>產品名稱</th>
                <th>分類</th>
                <th>件/</th>
                <th>購買件數</th>
                <th>件價</th>
                <th>上次購買日期</th>
            </tr>
        </thead>
        <tbody id="tableBody">
            <!-- 從 Excel 售價表中提取數據（移除進豐） -->
            <tr data-date="2025-03-04" data-category="梨">
                <td>大和</td>
                <td>智利紅梨20磅</td>
                <td>梨</td>
                <td>件</td>
                <td>50.0</td>
                <td>45.0</td>
                <td>4/3/2025</td>
            </tr>
            <tr data-date="2025-03-04" data-category="桃">
                <td>裕興</td>
                <td>天桃58個</td>
                <td>桃</td>
                <td>件</td>
                <td>30.0</td>
                <td>100.0</td>
                <td>4/3/2025</td>
            </tr>
            <tr data-date="2025-03-04" data-category="檸檬">
                <td>大和</td>
                <td>埃及檸檬100個</td>
                <td>檸檬</td>
                <td>件</td>
                <td>30.0</td>
                <td>105.0</td>
                <td>4/3/2025</td>
            </tr>
            <tr data-date="2025-03-04" data-category="檸檬">
                <td>興隆</td>
                <td>青檸1Kg</td>
                <td>檸檬</td>
                <td>件</td>
                <td>1.0</td>
                <td>45.0</td>
                <td>4/3/2025</td>
            </tr>
            <tr data-date="2025-03-04" data-category="蘋果">
                <td>大和</td>
                <td>美國蛇果100個</td>
                <td>蘋果</td>
                <td>件</td>
                <td>49.0</td>
                <td>155.0</td>
                <td>4/3/2025</td>
            </tr>
            <tr data-date="2025-03-04" data-category="提子">
                <td>大和</td>
                <td>秘魯紅提18磅</td>
                <td>提子</td>
                <td>件</td>
                <td>60.0</td>
                <td>100.0</td>
                <td>4/3/2025</td>
            </tr>
            <tr data-date="2025-03-04" data-category="提子">
                <td>滿棧</td>
                <td>秘魯波子提9磅</td>
                <td>提子</td>
                <td>件</td>
                <td>60.0</td>
                <td>160.0</td>
                <td>4/3/2025</td>
            </tr>
            <tr data-date="2025-03-04" data-category="車厘子">
                <td>裕興</td>
                <td>智利車厘子3j11磅</td>
                <td>車厘子</td>
                <td>件</td>
                <td>90.0</td>
                <td>150.0</td>
                <td>4/3/2025</td>
            </tr>
            <tr data-date="2025-03-04" data-category="瓜">
                <td>東記</td>
                <td>木瓜泡沫箱24個</td>
                <td>瓜</td>
                <td>件</td>
                <td>30.0</td>
                <td>50.0</td>
                <td>4/3/2025</td>
            </tr>
            <tr data-date="2025-03-04" data-category="其他">
                <td>東記</td>
                <td>大陸番薯18包</td>
                <td>其他</td>
                <td>件</td>
                <td>5.0</td>
                <td>90.0</td>
                <td>4/3/2025</td>
            </tr>
            <tr data-date="2025-03-04" data-category="火龍果">
                <td>東記</td>
                <td>紅火龍果27個</td>
                <td>火龍果</td>
                <td>件</td>
                <td>30.0</td>
                <td>90.0</td>
                <td>4/3/2025</td>
            </tr>
            <tr data-date="2025-03-03" data-category="提子">
                <td>富潤</td>
                <td>秘魯波子提9磅</td>
                <td>提子</td>
                <td>件</td>
                <td></td>
                <td>165.0</td>
                <td>3/3/2025</td>
            </tr>
            <tr data-date="2025-03-03" data-category="奇異果">
                <td>滿棧</td>
                <td>希臘奇異果25個</td>
                <td>奇異果</td>
                <td>件</td>
                <td>80.0</td>
                <td>20.0</td>
                <td>3/3/2025</td>
            </tr>
            <tr data-date="2025-03-03" data-category="柑">
                <td>東記</td>
                <td>大陸澳柑100個</td>
                <td>柑</td>
                <td>件</td>
                <td></td>
                <td>30.0</td>
                <td>3/3/2025</td>
            </tr>
            <tr data-date="2025-03-03" data-category="布冧">
                <td>東記</td>
                <td>智利紅布冧26個</td>
                <td>布冧</td>
                <td>件</td>
                <td></td>
                <td>50.0</td>
                <td>3/3/2025</td>
            </tr>
            <tr data-date="2025-03-03" data-category="車厘子">
                <td>東記</td>
                <td>智利車厘子3j11磅</td>
                <td>車厘子</td>
                <td>件</td>
                <td></td>
                <td>160.0</td>
                <td>3/3/2025</td>
            </tr>
        </tbody>
    </table>

    <script>
        // 儲存原始數據
        const originalRows = Array.from(document.getElementById("tableBody").getElementsByTagName("tr"));

        function searchTable() {
            // 獲取搜尋框中的值並轉為小寫
            var input = document.getElementById("search").value.toLowerCase();
            var tableBody = document.getElementById("tableBody");

            // 過濾匹配的行
            var filteredRows = originalRows.filter(row => {
                var cells = row.getElementsByTagName("td");
                for (var j = 0; j < cells.length; j++) {
                    var cellText = cells[j].innerText || "";
                    if (cellText.toLowerCase().includes(input)) {
                        return true;
                    }
                }
                return false;
            });

            // 按日期（降序）然後分類（升序）排序
            filteredRows.sort((a, b) => {
                var dateA = new Date(a.getAttribute("data-date"));
                var dateB = new Date(b.getAttribute("data-date"));
                if (dateA.getTime() !== dateB.getTime()) {
                    return dateB - dateA; // 日期降序
                }
                var catA = a.getAttribute("data-category");
                var catB = b.getAttribute("data-category");
                return catA.localeCompare(catB); // 分類升序
            });

            // 清空表格並重新添加排序後的行
            tableBody.innerHTML = "";
            filteredRows.forEach(row => {
                tableBody.appendChild(row.cloneNode(true)); // 使用複製的節點
            });

            // 如果搜尋框為空，顯示所有行並按日期和分類排序
            if (!input) {
                var sortedRows = originalRows.slice().sort((a, b) => {
                    var dateA = new Date(a.getAttribute("data-date"));
                    var dateB = new Date(b.getAttribute("data-date"));
                    if (dateA.getTime() !== dateB.getTime()) {
                        return dateB - dateA;
                    }
                    var catA = a.getAttribute("data-category");
                    var catB = b.getAttribute("data-category");
                    return catA.localeCompare(catB);
                });
                sortedRows.forEach(row => {
                    tableBody.appendChild(row.cloneNode(true));
                });
            }
        }

        // 初始化時按日期和分類排序
        searchTable();
    </script>
</body>
</html>
