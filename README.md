# today

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://code.jquery.com/jquery-3.7.1.js"></script>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/js/bootstrap.bundle.min.js"></script>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.2/jquery.min.js"></script>
    <script src="https://code.jquery.com/jquery-3.7.1.js"></script>
    <style>
        .fakeimg {
            height: 200px;
            background: #aaa;
        }

        body {
            background-color: rgb(52, 52, 57);
            color: white;
            margin: 0;
        }

        .nav {
            height: 60px;
            border-bottom: 1px solid black;
            display: flex;
            align-items: center;
            justify-content: space-between;
            background-color: #2a2a30;
            margin: 0;
            padding: 0 20px;
        }

        .nav-right-items {
            display: flex;
        }

        .nav-item,
        .company-name {
            color: rgb(255, 255, 255);
        }

        .nav-item {
            margin-left: 10px;
        }

        .company-name {
            margin-left: 20px;
            font-weight: bold;
        }

        .title {
            text-align: center;
            font-size: 3.5rem;
            margin-top: 80px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .title img {
            max-width: 100px;
            max-height: 100px;
            margin-right: 20px;
        }

        .subtitle {
            text-align: center;
            font-size: 1.25rem;
            font-weight: 300;
        }

        .main {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            margin-right: 50px;
            margin-top: -15px;
        }

        .prices {
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: row;
            gap: 20px;
        }

        .price-item {
            position: relative;
            width: 300px;
            height: 300px;
            border: 1px solid rgb(129, 127, 127);
            margin: 20px;
            border-radius: 4px;
            background-color: rgb(255, 255, 255);
            background-position: center;
            background-size: cover;
            background-repeat: no-repeat;
            border-radius: 20px;
        }

        .price-item-title {
            font-size: 1.5rem;
            background: rgb(232, 234, 237);
            text-align: center;
            height: 53px;
            line-height: 53px;
            border-bottom: 1px solid black;
            color: black;
        }

        .price-item-button {
            padding: .5rem 1rem;
            font-size: 1.25rem;
            line-height: 1.5;
            border-radius: .3rem;
            color: #ff0000;
            background-color: transparent;
            background-image: none;
            border-color: #000000;
            position: relative;
            left: -85px;
            margin-top: 0px;
            transform: translateX(43%);
        }

        .price-item-button--active {
            background-color: #d62222;
            color: white;
        }

        #fileform {
            margin-top: 0;
        }

        #results,
        #resultr {
            background-color: rgb(255, 255, 255);
            border: 1px solid rgb(110, 109, 109);
            margin-top: 20px;
            margin-left: 20px;
        }

        #textkan {
            margin-top: -189px;
            margin-right: 380px;
            text-align: center;
            border: none;
            resize: none;
            border-radius: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 8px 100px;
        }

        #textkaan {
            margin-top: -41px;
            margin-right: -380px;
            text-align: center;
            border: none;
            resize: none;
            border-radius: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 8px 100px;

            
        }

        #gimage {
            margin: 20px;
            border-radius: 20px;
        }


        .upload-section {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            margin-left: 85px;
            margin-top: 80px;
        }

        .result-section {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
        }

        /* "그림에 대해 말씀하세요" 섹션의 스타일 수정 */
        .input-group.mb-3 {
            max-width: 300px;
            margin: auto;
        }

        .form-control {
            width: 100%;
        }

        .btn.btn-success {
            width: 100%;
        }

        .input-group.mb-3 {
            max-width: 300px;
            margin: auto;
            display: none;
        }

    </style>
</head>

<body>
    <!-- 네비게이션 및 메인 섹션 -->
    <div class="nav">
        <div class="company-name">
            Image Analysis
        </div>
    </div>
    <div class="main">
        <!-- 이미지 분석 섹션 -->
        <div class="title">
            <img src="./현미경.png" alt="이미지">
            Image Analysis
        </div>
        <div class="subtitle">이미지 분석 웹 페이지입니다.<br> 파일 선택에서 분석하고자 하는 이미지를 선택한 뒤 Submit을 눌러주세요.</div>
        <div class="prices">
            <!-- 이미지 표시 섹션 -->
            <div class="price-item" id="image-container"></div>
            <!-- 결과 표시 섹션 -->
            <div class="result-section">
                <textarea name="results" id="results" cols="50" rows="10" style="display: none;"></textarea>
                <textarea name="resultr" id="resultr" cols="50" rows="10" style="display: none;"></textarea>
            </div>
            <img id="gimage" style="border: 5px solid #555; background-color: rgb(255, 255, 255); width: 300px; height: 300px; ">
        </div>
        <!-- 이미지 업로드 및 분석 섹션 -->
        <div class="upload-section">
            <div>
                <!-- 이미지 업로드 폼 -->
                <input type="file" name="fileField" id="fileField" onChange="uploadFiles(this.files)">
                <!-- 이미지 타입 선택 폼 -->
                <form id="fileform" action="">
                    <select name="type" id="detectionType" style="display: none;">
                        <option value="LABEL_DETECTION" selected>LABEL_DETECTION</option>
                    </select>
                </form>
            </div>
            <!-- 이미지 분석 버튼 -->
            <button class="price-item-button price-item-button--active" onclick="Send()">Submit</button>
            <!-- 추가 버튼 (예: 대답하기) -->
            <button class="btn btn-success" type="submit" onclick="Draw()" id="btnSend" style="display: none;">대답하기</button>
        </div>
    <button name="textkan" id="textkan" cols="37" rows="2" font size="60">선택한 이미지</button>
    <button name="textkaan" id="textkaan" cols="37" rows="2">비슷한 이미지</button>
    </div>
    <!-- 그림에 대해 말씀하세요 섹션 -->
    <div class="input-group mb-3">
        <input type="text" class="form-control" placeholder="그림에 대해 말씀하세요" id="imgMsg">
    </div>

    <!-- 추가 스크립트 -->
    <script src="chat.js"></script>
    <script>
        // 이미지 관련 코드 및 함수
        var VISION_API_KEY = "A3333333333333333333333333333333333IzaSyDLIcg-VsVJ3RgsW8-cI76Zrsp1_qkTBAA";
        var CV_URL = 'https://vision.googleapis.com/v1/images:annotate?key=' + VISION_API_KEY;
        var imagestring = "";

        // 파일 처리 함수
        function processFile(event) {
            var content = event.target.result;
            imagestring = content.replace('data:image/jpeg;base64,', '');

            // 이미지를 미리보기로 표시
            var imageContainer = document.getElementById('image-container');
            imageContainer.style.backgroundImage = 'url(' + content + ')';
            imageContainer.style.backgroundPosition = 'center';
            imageContainer.style.backgroundSize = 'cover';
            imageContainer.style.backgroundRepeat = 'no-repeat';
        }

        // 파일 업로드 함수
        function uploadFiles(files) {
            var file = files[0];
            var reader = new FileReader();
            reader.onloadend = function (event) {
                processFile(event);
                // 이미지 업로드 시 select를 LABEL_DETECTION으로 변경
                document.getElementById('detectionType').value = 'LABEL_DETECTION';
            };
            reader.readAsDataURL(file);
        }

        // 이미지 분석 및 결과 표시 함수
        function Send() {
            var detectionType = $('#fileform select[name=type]').val();
            console.log("Detection Type:", detectionType);

            var request = {
                requests: [{
                    image: {
                        content: imagestring
                    },
                    features: [{
                        type: detectionType,
                        maxResults: 200
                    }]
                }]
            };

            $.ajax({
                type: "POST",
                url: CV_URL,
                headers: {
                    "Accept": "application/json",
                    "Content-Type": "application/json"
                },
                data: JSON.stringify(request),
                contentType: "application/json; charset=utf-8"
            }).done(function (response) {
                // displayJSON 함수 호출 (가정: 이 함수가 정의되어 있다고 가정)
                displayJSON(response);

                // resultr 텍스트 영역의 내용을 가져와서 imgMsg 입력 필드에 설정
                var resultrText = $('#resultr').val();
                $('#imgMsg').val(resultrText);

                // "btnSend" 버튼 클릭
                $('#btnSend').click();
            }).fail(function (error) {
                alert("!/error  js에서 에러발생: " + error);
            });
        }

        // displayJSON 함수 추가
        function displayJSON(data) {
            var contents = JSON.stringify(data, null, 4);
            $('#results').text(contents);

            var dlabels = "";
            var labels = data.responses[0].labelAnnotations;

            console.log(labels);

            labels.forEach(function (label) {
                dlabels += label.description + "\n";
            });
            $('#resultr').text(dlabels);
        }
    </script>
</body>

</html>
