<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>상품 구매 페이지</title>
    <style>
        /* 스타일 시트 */
        body {
            font-family: Arial, sans-serif;
        }
        .container {
            max-width: 400px;
            margin: 50px auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        select, input[type="text"], textarea, button {
            width: 100%;
            padding: 12px;
            margin-bottom: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
            box-sizing: border-box;
        }
        textarea {
            height: 80px; /* 높이 조정 */
        }
        button {
            background-color: #333;
            color: #fff;
            cursor: pointer;
        }
        .account-info {
            margin-top: 20px;
            padding: 10px;
            background-color: #f9f9f9;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>상품 구매</h2>
        
        <div>
            <label for="edition-select">에디션 선택:</label>
            <select id="edition-select">
                <option value="권동원 에디션">권동원 에디션</option>
                <option value="그냥뉴비 에디션">그냥뉴비 에디션</option>
                <option value="이원만 에디션">이원만 에디션</option>
            </select>
        </div>

        <div>
            <label for="price-input">가격:</label>
            <input type="text" id="price-input" value="₩10,000" readonly style="font-size: 18px;">
        </div>

        <div>
            <label for="discord-username">디스코드 계정 사용자명:</label>
            <input type="text" id="discord-username" placeholder="예: orignal_noob">
        </div>

        <div>
            <label for="payer-name">입금자명:</label>
            <input type="text" id="payer-name" placeholder="입금자명을 입력하세요">
        </div>

        <div>
            <label for="shipping-address">배송 주소:</label>
            <textarea id="shipping-address" placeholder="배송 주소를 입력하세요"></textarea>
        </div>

        <button onclick="purchase()">구매하기</button>

        <div class="account-info">
            <h3>계좌번호(선불입니다. 저희는 실시간으로 확인하고있습니다. 선금이 들어오지않을 경우 택배가 발송돼지 않습니다.)</h3>
            <p>508-13-446817-8</p>
            <p>대구은행</p>
            <h3>배송비</h3>
            <p>₩3,000까지 무료</p>
        </div>
    </div>

    <script>
        function purchase() {
            var editionSelect = document.getElementById("edition-select");
            var selectedEdition = editionSelect.options[editionSelect.selectedIndex].value;
            var priceInput = document.getElementById("price-input").value;
            var discordUsername = document.getElementById("discord-username").value;
            var payerName = document.getElementById("payer-name").value;
            var shippingAddress = document.getElementById("shipping-address").value;
            var message = "에디션: " + selectedEdition + "\n가격: " + priceInput + "\n디스코드 계정 사용자명: " + discordUsername + "\n입금자명: " + payerName + "\n배송 주소: " + shippingAddress;

            // 디스코드 DM 보내기
            var discordWebhookURL = "https://discord.com/api/webhooks/1218472413990355014/r-Kl-p4aTM0uW383wIz7ZAC1lPFdH6VQkELn1pYyXtZK_TBaE9h0YjDCTrFvQJpB76xz";
            var discordMessage = {
                content: message
            };

            fetch(discordWebhookURL, {
                method: "POST",
                headers: {
                    "Content-Type": "application/json"
                },
                body: JSON.stringify(discordMessage)
            }).then(response => {
                if (response.ok) {
                    alert("구매 정보가 디스코드로 전송되었습니다.");
                } else {
                    alert("구매 정보 전송에 실패했습니다.");
                }
            }).catch(error => {
                alert("구매 정보 전송 중 오류가 발생했습니다: " + error);
            });
        }
    </script>
</body>
</html>
