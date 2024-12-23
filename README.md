<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>내란 범죄혐의자 명단</title>
    <style>
        /* 공통 스타일 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;  
            margin: 0;
            padding: 20px;
            color: #333;    
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background-color: #fff;
            padding: 30px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            width: 100%;
        }

        h1 {
            text-align: center;
            color: white;
            background-color: #8b0000;
            padding: 20px;
            margin: -30px -30px 30px;
            font-size: 28px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }

        /* 섹션 스타일 */
        .section {
            margin-bottom: 40px;
            padding-bottom: 20px;
            text-align: center;
        }

        /* 내란수괴 섹션 특별 스타일 */
        #내란수괴-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        #내란수괴-container .person-container:first-child {
            margin: 0 auto;  /* 윤석열 중앙 배치 */
        }

        #내란수괴-container .person-container:last-child {
            margin-left: auto;  /* 김건희 오른쪽 배치 */
        }

        /* 섹션 헤더 스타일 */
        .section-header {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-bottom: 20px;
        }

        /* 섹션 로고 스타일 */
        .section-logo {
            max-width: 150px;
            width: 100%;
            margin-bottom: 20px;
        }

        /* 내란의힘 로고 크기 조절 */
        #내란의힘-section .section-logo {
            max-width: 50px;  /* 80px에서 50px로 감소 */
        }

        /* 군부 로고 크기 조절 */
        #군부-section .section-logo {
            max-width: 180px;
        }

        /* 섹션 제목 스타일 */
        #내란수괴-section h2,
        #군부-section h2,
        #경찰-section h2,
        #대통령실-section h2,
        #내란의힘-section h2,
        #기타·극우미디어-section h2 {
            color: #000;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom-width: 4px;
            border-bottom-style: solid;
            text-align: center;
            font-size: 24px;
            position: relative;
            width: 80%;
            display: inline-block;
        }

        /* 섹션별 테두리 색상 */
        #내란수괴-section h2 {
            border-bottom-color: #8b0000;  /* 진한 빨강 */
        }

        #군부-section h2 {
            border-bottom-color: #006400;  /* 진한 초록 */
        }

        #경찰-section h2 {
            border-bottom-color: #00008b;  /* 진한 파랑 */
        }

        #대통령실-section h2 {
            border-bottom-color: #4b0082;  /* 남색 */
        }

        #내란의힘-section h2 {
            border-bottom-color: #E61E2B;  /* 빨간색 */
        }

        #기타·극우미디어-section h2 {
            border-bottom-color: #2f4f4f;  /* 진한 회색 */
        }

        .section h2 span {
            display: block;
            margin-top: 10px;
        }

        /* 모바일 화면에서 섹션 여백 조정 */
        @media screen and (max-width: 767px) {
            #내란수괴-section h2,
            #군부-section h2,
            #경찰-section h2,
            #대통령실-section h2,
            #내란의힘-section h2,
            #기타·극우미디어-section h2 {
                font-size: 15px !important;
                margin-bottom: 5px;
            }

            #내란수괴-section {
                margin-bottom: 20px;
                padding-bottom: 10px;
            }

            #내란수괴-container {
                margin-top: -30px;
            }

            #군부-container {
                margin-top: -10px;
            }

            #군부-section {
                margin-top: -15px;
            }

            #군부-section img {
                margin-bottom: 5px;
            }

            #경찰-section {
                margin-top: -15px;
            }

            #경찰-section img {
                width: 35px;  
                margin-bottom: 3px;
            }

            #경찰-container {
                margin-top: -10px;
            }

            #대통령실-container {
                margin-top: -10px;
            }

            #대통령실-section {
                margin-top: -15px;
            }

            #대통령실-section img {
                margin-bottom: 3px;
            }

            #대통령실-section h2 {
                margin-top: 2px !important;
            }

            #기타·극우미디어-section .section-logo {
                max-width: 50px;  /* 로고 크기 줄임 */
            }

            /* 섹션 제목 폰트 크기 조정 */
            .section h2 {
                font-size: 15px;
            }
        }

        /* 필터 버튼 스타일 */
        .filters {
            display: flex;
            flex-wrap: nowrap;
            justify-content: center;
            gap: 5px;
            margin: 20px 0;
            width: 100%;
            padding: 0 10px;
            box-sizing: border-box;
        }

        .filter-btn {
            padding: 8px 12px;
            border: 2px solid #8b0000;
            background: none;
            color: #8b0000;
            cursor: pointer;
            border-radius: 5px;
            flex: 1 1 auto;
            min-width: 0;
            white-space: nowrap;
            font-size: 14px;
            transition: all 0.3s ease;
            text-overflow: ellipsis;
            overflow: hidden;
        }

        .filter-btn:hover {
            background: #8b0000;
            color: white;
        }

        .filter-btn.active {
            background: #8b0000;
            color: white;
        }

        /* 섹션별 스타일 */
        #군부 {
            background: rgba(38, 50, 56, 0.05);  
            border-radius: 15px;
            padding: 20px;
        }

        #대통령실 {
            background: rgba(19, 41, 75, 0.05);
            border-radius: 15px;
            padding: 20px;
        }

        #정치인 {
            background: rgba(211, 47, 47, 0.05);
            border-radius: 15px;
            padding: 20px;
            margin: 0 auto;
            width: 100%;
            box-sizing: border-box;
            overflow: hidden;
        }

        #경찰 {
            background: rgba(211, 47, 47, 0.05);
            border-radius: 15px;
            padding: 20px;
        }

        #기타·극우미디어 {
            background: rgba(244, 67, 54, 0.05);
            border-radius: 15px;
            padding: 20px;
        }

        /* 인물 카드 레이아웃 스타일 */
        .people-container {
            display: flex;
            flex-wrap: wrap;
            gap: 5px;
            justify-content: center;
            padding: 10px;
            width: 100%;
            box-sizing: border-box;
        }

        .row {
            display: flex;
            flex-wrap: nowrap;
            gap: 5px;
            justify-content: center;
            width: 100%;
        }

        .person-container {
            position: relative;
            width: calc((100% - 35px) / 8);
            flex: 0 0 calc((100% - 35px) / 8);
            margin-bottom: 10px;
            text-align: center;
            display: flex;
            flex-direction: column;
            align-items: center;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .person-container:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .person-container img {
            width: 100%;
            aspect-ratio: 3/4;
            object-fit: cover;
            border-radius: 4px;
            margin-bottom: 5px;
        }

        .person-name {
            font-size: 15px;
            font-weight: bold;
            margin: 5px 0 3px 0;
            width: 100%;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            color: #000;
        }

        .person-role {
            font-size: 11px;
            color: #444;
            margin: 2px 0;
            width: 100%;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            font-weight: 500;
        }

        .person-role2 {
            font-size: 9px;
            color: #666;
            margin-top: 1px;
            width: 100%;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
        }

        /* 계엄해제 불참자 그룹 스타일 */
        .martial-law-group {
            border: 3px solid #ff4444;
            padding: 10px;
            margin: 10px 0;
            position: relative;
        }
        
        .martial-law-group::before {
            content: '계엄해제 불참자';
            position: absolute;
            top: -12px;
            left: 10px;
            background-color: white;
            padding: 0 10px;
            color: #ff4444;
            font-weight: bold;
        }

        /* 계엄해제 동의자 그룹 스타일 */
        .martial-law-agree-group {
            border: 3px solid #2f842f;
            padding: 10px;
            margin: 10px 0;
            position: relative;
        }
        
        .martial-law-agree-group::before {
            content: '계엄해제 동의자';
            position: absolute;
            top: -12px;
            left: 10px;
            background-color: white;
            padding: 0 10px;
            color: #2f842f;
            font-weight: bold;
        }
        
        /* 반응형 디자인 */
        @media screen and (max-width: 768px) {
            .filters {
                padding: 0 5px;
                gap: 3px;
            }

            .filter-btn {
                padding: 5px;
                font-size: 11px;
                border-width: 1px;
            }

            .people-container {
                padding: 5px;
                gap: 5px;  /* 2px에서 5px로 증가 */
            }

            .row {
                gap: 5px;  /* 3px에서 5px로 증가 */
            }

            .person-container {
                width: calc((100% - 21px) / 8);
                flex: 0 0 calc((100% - 21px) / 8);
                margin-bottom: 15px;  /* 세로 간격 추가 */
            }

            .person-container img {
                margin-bottom: 2px;
            }

            .person-name {
                font-size: 8px;
                margin: 2px 0 1px 0;
            }

            .person-role {
                font-size: 5.5px;
                margin: 1px 0;
            }

            .person-role2 {
                font-size: 5px;
                margin-top: 1px;
            }
        }

        @media screen and (max-width: 480px) {
            .filters {
                gap: 2px;
            }

            .filter-btn {
                padding: 3px 4px;
                font-size: 9px;
            }

            .person-container {
                width: calc((100% - 14px) / 8);
                flex: 0 0 calc((100% - 14px) / 8);
            }

            .person-name {
                font-size: 7px;
            }

            .person-role {
                font-size: 4.5px;
                margin: 1px 0;
            }

            .person-role2 {
                font-size: 4px;
                margin-top: 0;
            }
        }

        /* 모바일 환경 스타일 */
        @media screen and (max-width: 768px) {
            .section-logo {
                max-width: 100px;
            }

            #내란의힘-section .section-logo {
                max-width: 50px;  /* 80px에서 50px로 감소 */
            }

            #군부-section .section-logo {
                max-width: 120px;
            }

            .section {
                margin-bottom: 30px;
                padding: 0 5px;
            }

            .people-container {
                display: flex;
                flex-wrap: wrap;
                justify-content: flex-start;
                gap: 5px;  /* 2px에서 5px로 증가 */
                padding: 0;
            }

            .person-card {
                width: calc((100% - 14px) / 8);  /* 8명씩 배치, 간격 2px 고려 */
                margin: 0;
                padding: 2px;
                border: none;
                box-shadow: none;
            }

            .person-card img {
                width: 100%;
                height: auto;
                margin-bottom: 2px;
            }

            .person-card .name {
                font-size: 10px;
                margin: 2px 0;
                line-height: 1.2;
            }

            .person-card .role {
                font-size: 9px;
                margin: 1px 0;
                line-height: 1.1;
            }
        }

        @media screen and (max-width: 480px) {
            .section-logo {
                max-width: 80px;
            }

            #내란의힘-section .section-logo {
                max-width: 50px;  /* 60px에서 50px로 감소 */
            }

            #군부-section .section-logo {
                max-width: 100px;
            }

            .people-container {
                gap: 5px;  /* 1px에서 5px로 증가 */
            }

            .person-card {
                width: calc((100% - 7px) / 8);  /* 8명씩 배치, 간격 1px 고려 */
                padding: 1px;
            }

            .person-card .name {
                font-size: 9px;
            }

            .person-card .role {
                font-size: 8px;
            }
        }

        #내란의힘-section .people-container {
            justify-content: center !important;
        }

        /* 하단 컨트롤 스타일 */
        .bottom-controls {
            position: fixed;
            bottom: 30px;
            right: 30px;
            display: flex;
            flex-direction: row;
            gap: 15px;
            z-index: 1000;
            align-items: center;
        }

        .search-container {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
            transition: all 0.3s ease;
            width: 200px;
            overflow: hidden;
            position: relative;
        }

        .search-container:focus-within {
            width: 250px;
            box-shadow: 0 4px 20px rgba(139, 0, 0, 0.2);
        }

        #searchInput {
            width: 100%;
            padding: 12px 20px;
            border: 2px solid transparent;
            border-radius: 25px;
            font-size: 14px;
            outline: none;
            transition: all 0.3s ease;
            background: transparent;
        }

        #searchInput:focus {
            border-color: #8b0000;
        }

        .scroll-top-btn {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: #8b0000;
            color: white;
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .scroll-top-btn:hover {
            background: #6b0000;
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(139, 0, 0, 0.25);
        }

        .scroll-top-btn::before {
            content: "↑";
            font-size: 20px;
            font-weight: bold;
        }

        /* 모바일 최적화 */
        @media screen and (max-width: 768px) {
            .bottom-controls {
                bottom: 20px;
                right: 20px;
                gap: 10px;
            }

            .search-container {
                width: 160px;
            }

            .search-container:focus-within {
                width: 200px;
            }

            #searchInput {
                padding: 10px 15px;
                font-size: 13px;
            }

            .scroll-top-btn {
                width: 40px;
                height: 40px;
            }   

            .scroll-top-btn::before {
                font-size: 18px;
            }
        }

        @keyframes highlight {
            0% { transform: scale(1); box-shadow: 0 0 0 rgba(139, 0, 0, 0); }
            50% { transform: scale(1.05); box-shadow: 0 0 20px rgba(139, 0, 0, 0.3); }
            100% { transform: scale(1); box-shadow: 0 0 0 rgba(139, 0, 0, 0); }
        }

        /* 검색 결과 스타일 */
        .search-container {
            position: relative;
        }

        .search-results {
            position: absolute;
            bottom: 100%;
            left: 0;
            right: 0;
            background: rgba(255, 255, 255, 0.98);
            border-radius: 15px;
            box-shadow: 0 -4px 20px rgba(0, 0, 0, 0.15);
            margin-bottom: 10px;
            max-height: 300px;
            overflow-y: auto;
            display: none;
            z-index: 1000;
        }

        .search-result-item {
            padding: 10px 15px;
            cursor: pointer;
            transition: all 0.2s ease;
            border-bottom: 1px solid rgba(0, 0, 0, 0.1);
        }

        .search-result-item:last-child {
            border-bottom: none;
        }

        .search-result-item:hover {
            background: rgba(139, 0, 0, 0.1);
        }

        .search-result-name {
            font-weight: bold;
            color: #8b0000;
        }

        .search-result-role {
            font-size: 0.9em;
            color: #666;
            margin-top: 3px;
        }

        /* 스크롤바 스타일 */
        .search-results::-webkit-scrollbar {
            width: 8px;
        }

        .search-results::-webkit-scrollbar-track {
            background: #f1f1f1;
            border-radius: 4px;
        }

        .search-results::-webkit-scrollbar-thumb {
            background: #8b0000;
            border-radius: 4px;
        }

        .search-results::-webkit-scrollbar-thumb:hover {
            background: #6b0000;
        }

        /* 모달 스타일 */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 2000;
        }

        .modal-content {
            position: relative;
            background-color: #fefefe;
            margin: 5% auto;
            padding: 20px;
            width: 80%;
            max-width: 800px;
            border-radius: 15px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
        }

        .modal-header {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #8b0000;
        }

        .modal-header img {
            width: 100px;
            height: 100px;
            object-fit: cover;
            border-radius: 50%;
            margin-right: 20px;
        }

        .modal-header-info h2 {
            margin: 0;
            color: #8b0000;
        }

        .modal-header-info p {
            margin: 5px 0;
            color: #666;
        }

        .modal-body {
            margin-bottom: 20px;
        }

        .modal-body textarea {
            width: 100%;
            min-height: 200px;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            resize: vertical;
            font-family: inherit;
        }

        .modal-footer {
            text-align: right;
        }

        .modal-close {
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 24px;
            cursor: pointer;
            color: #8b0000;
        }

        .save-btn {
            background-color: #8b0000;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .save-btn:hover {
            background-color: #6b0000;
        }

        .admin-btn {
            background-color: #8b0000;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .admin-btn:hover {
            background-color: #6b0000;
        }

        .pending-message {
            font-size: 14px;
            color: #666;
            margin: 10px 0;
        }

        .actions-text {
            font-size: 14px;
            color: #333;
            margin: 10px 0;
        }

        /* 공지사항 팝업 스타일 */
        .notice-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 3000;
        }

        .notice-content {
            position: relative;
            background-color: #fefefe;
            margin: 10% auto;
            padding: 30px;
            width: 80%;
            max-width: 600px;
            border-radius: 15px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
        }

        .notice-title {
            color: #8b0000;
            font-size: 24px;
            margin-bottom: 20px;
        }

        .notice-text {
            font-size: 16px;
            line-height: 1.6;
            margin-bottom: 20px;
            white-space: pre-line;
        }

        .notice-close {
            background-color: #8b0000;
            color: white;
            border: none;
            padding: 10px 30px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s;
        }

        .notice-close:hover {
            background-color: #6b0000;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>내란 범죄혐의자 명단</h1>
        
        <!-- 필터 버튼 -->
        <div class="filters">
            <button onclick="document.getElementById('군부-section').scrollIntoView({ behavior: 'smooth' })" class="filter-btn">군부</button>
            <button onclick="document.getElementById('경찰-section').scrollIntoView({ behavior: 'smooth' })" class="filter-btn">경찰</button>
            <button onclick="document.getElementById('대통령실-section').scrollIntoView({ behavior: 'smooth' })" class="filter-btn">대통령실</button>
            <button onclick="document.getElementById('내란의힘-section').scrollIntoView({ behavior: 'smooth' })" class="filter-btn">내란의힘</button>
            <button onclick="document.getElementById('기타·극우미디어-section').scrollIntoView({ behavior: 'smooth' })" class="filter-btn">기타·극우미디어</button>
        </div>

        <!-- 내란수괴 섹션 -->
        <div class="section" id="내란수괴-section">
            <div class="section-header">
                <h2>내란수괴</h2>
            </div>
            <div class="people-container" id="내란수괴-container"></div>
        </div>

        <!-- 군부 섹션 -->
        <div class="section" id="군부-section">
            <div class="section-header">
                <img src="images/군부/군부.jpeg" alt="군부 로고" class="section-logo">
                <h2>군부</h2>
            </div>
            <div class="people-container" id="군부-container"></div>
        </div>

        <!-- 경찰 섹션 -->
        <div class="section" id="경찰-section">
            <div class="section-header">
                <img src="images/경찰/경찰.jpeg" alt="경찰 로고" class="section-logo">
                <h2>경찰</h2>
            </div>
            <div class="people-container" id="경찰-container"></div>
        </div>

        <!-- 대통령실 섹션 -->
        <div class="section" id="대통령실-section">
            <div class="section-header">
                <img src="images/대통령실/대통령실.jpeg" alt="대통령실 로고" class="section-logo">
                <h2 style="margin-top: 10px;">대통령실</h2>
            </div>
            <div class="people-container" id="대통령실-container"></div>
        </div>

        <!-- 내란의힘 섹션 -->
        <div class="section" id="내란의힘-section">
            <div class="section-header">
                <img src="images/내란의힘/내란의힘.jpeg" alt="내란의힘 로고" class="section-logo">
                <h2>내란의힘</h2>
            </div>
            <div class="people-container" id="내란의힘-container"></div>
        </div>

        <!-- 기타·극우미디어 섹션 -->
        <div class="section" id="기타·극우미디어-section">
            <div class="section-header">
                <img src="images/기타·극우미디어/기타·극우미디어.jpg" alt="기타·극우미디어 로고" class="section-logo">
                <h2>기타·극우미디어</h2>
            </div>
            <div class="people-container" id="기타·극우미디어-container"></div>
        </div>
    </div>

    <!-- 하단 컨트롤 -->
    <div class="bottom-controls">
        <div class="search-container">
            <div class="search-results"></div>
            <input type="text" id="searchInput" placeholder="이름 또는 행적 검색...">
        </div>
        <button class="scroll-top-btn" title="맨 위로 이동"></button>
    </div>

    <!-- 모달 창 -->
    <div id="personModal" class="modal">
        <div class="modal-content">
            <span class="modal-close">&times;</span>
            <div class="modal-header">
                <img id="modalImage" src="" alt="">
                <div class="modal-header-info">
                    <h2 id="modalName"></h2>
                    <p id="modalRole1"></p>
                    <p id="modalRole2"></p>
                </div>
            </div>
            <div class="modal-body">
                <div id="modalActionsView"></div>
                <textarea id="modalActions" placeholder="이 사람의 행적을 입력하세요..." style="display: none;"></textarea>
            </div>
            <div class="modal-footer">
                <button id="adminLoginBtn" class="admin-btn">관리자 로그인</button>
                <button id="saveBtn" class="save-btn" style="display: none;">저장</button>
            </div>
        </div>
    </div>

    <!-- 관리자 로그인 모달 -->
    <div id="adminModal" class="modal">
        <div class="modal-content" style="max-width: 400px;">
            <span class="modal-close">&times;</span>
            <div class="modal-header">
                <h2>관리자 로그인</h2>
            </div>
            <div class="modal-body">
                <input type="password" id="adminPassword" placeholder="관리자 비밀번호를 입력하세요" style="width: 100%; padding: 10px; margin: 10px 0;">
            </div>
            <div class="modal-footer">
                <button onclick="checkAdminPassword()" class="save-btn">로그인</button>
            </div>
        </div>
    </div>

    <!-- 공지사항 모달 -->
    <div id="noticeModal" class="notice-modal">
        <div class="notice-content">
            <h2 class="notice-title">공지사항</h2>
            <div class="notice-text">
내란 범죄혐의자 리스트입니다.
❗사이트를 함께 관리해주실 웹 디자이너, 개발자 분들을 찾습니다.❗
❗각 인물들의 행적을 같이 조사해주실 국민여러분들을 찾습니다.❗
criminalyoon@gmail.com
각 인물을 클릭하면 자세한 행적을 볼 수 있습니다.
검색창에서 이름이나 행적으로 검색할 수 있습니다.
계속해서 업데이트 중입니다.</div>
            <button class="notice-close" onclick="closeNotice()">확인</button>
        </div>
    </div>

    <script>
        const people = [ 
            
            // 내란수괴
            { name: "윤석열", role1: "내란수괴1", role2: "대통령", group: "내란수괴", row: 1, position: "center" },
            { name: "김건희", role1: "대한민국 최고존엄", role2: "대통령부인", group: "내란수괴", row: 1, position: "right" },

            // 군 관계자
            { name: "김용현", role1: "내란수괴2", role2: "국방부장관", group: "군부", row: 1 },
            { name: "노상원", role1: "내란수괴3", role2: "전정보사령관, 성범죄자", group: "군부", row: 2 },
            { name: "여인형", role1: "내란수괴4", role2: "방첩사령관", group: "군부", row: 2 },
            { name: "박안수", role1: "내란주동자", role2: "계엄사령관", group: "군부", row: 3 }, 
            { name: "정진팔", role1: "내란주동자", role2: "계엄부사령관", group: "군부", row: 3 },
            { name: "문상호", role1: "내란주동자", role2: "정보사령관", group: "군부", row: 3 },
            { name: "이진우", role1: "내란주동자", role2: "수방사령관", group: "군부", row: 3 },
            { name: "곽종근", role1: "내란주동자", role2: "특전사령관", group: "군부", row: 3 },
            { name: "박종선", role1: "내란주동자", role2: "777사령관", group: "군부", row: 3 },
            { name: "구삼회", role1: "내란주동자", role2: "제2기갑여단장", group: "군부", row: 3 },
            { name: "김대우", role1: "내란주동잔자", role2: "방첩사수사단장", group: "군부", row: 3 },
            { name: "이경민", role1: "내란가담자", role2: "방첩사참모장", group: "군부", row: 4 },
            { name: "안무성", role1: "내란가담자", role2: "제9공수여단장", group: "군부", row: 4 },
            { name: "박성하", role1: "내란가담자", role2: "방첩사기획관리실장", group: "군부", row: 4 },
            { name: "나승민", role1: "내란가담자", role2: "방첩사신원보안실장", group: "군부", row: 4 },
            { name: "김철진", role1: "내란가담자", role2: "국방부군사보좌관", group: "군부", row: 4 },
            { name: "이상현", role1: "내란가담자", role2: "제1공수특전여단장", group: "군부", row: 4 },
            { name: "조종래", role1: "내란가담자", role2: "육군정보참모부장", group: "군부", row: 4 },
            { name: "김현태", role1: "내란가담자", role2: "707특임단장", group: "군부", row: 5 },
            { name: "김세운", role1: "부화내동자", role2: "작전항공단장", group: "군부", row: 5 },
            { name: "정성우", role1: "부화내동자", role2: "방첩사1처장", group: "군부", row: 5 },

            // 경찰
            { name: "김봉식", role1: "내란주동자", role2: "서울경찰청장", group: "경찰", row: 1,},
            { name: "조지호", role1: "내란주동자", role2: "경찰청장", group: "경찰", row: 1,},
            { name: "강상문", role1: "내란주동자", role2: "영등포서장", group: "경찰", row: 1, },
            { name: "목현태", role1: "내란주동자", role2: "국회경비대장", group: "경찰", row: 2,},
            { name: "최창복", role1: "내란주동잔자", role2: "서울경비안전계장", group: "경찰", row: 2,},

            // 행정부
            // 1열: 핵심 인물
            { name: "한덕수", role1: "내란동조자", role2: "국무총리", group: "대통령실", row: 1 },
            { name: "이상민", role1: "내란주동자", role2: "행안부장관", group: "대통령실", row: 1 },
            { name: "박성재", role1: "내란동조자", role2: "법무부장관", group: "대통령실", row: 1 },
            { name: "이완규", role1: "내란동조자", role2: "법제처장", group: "대통령실", row: 1 },
            { name: "김주현", role1: "내란동조자", role2: "민정수석", group: "대통령실", row: 1 },

            // 2열: 기타 인물
            { name: "인성환", role1: "내란동조자", role2: "안보실2차장", group: "대통령실", row: 2 },
            { name: "최병옥", role1: "내란동조자", role2: "국방비서관", group: "대통령실", row: 2 },
            { name: "정진석", role1: "내란동조자", role2: "비서실장", group: "대통령실", row: 2 },     
            { name: "박종준", role1: "내란동조자", role2: "경호처장", group: "대통령실", row: 2 },
            { name: "김문수", role1: "내란동조자", role2: "고용노동부장관", group: "대통령실", row: 2 },
            { name: "김태규", role1: "내란동조자", role2: "방통위부위원장", group: "대통령실", row: 2 },
            { name: "유창호", role1: "내란동조자", role2: "외교부부대변인", group: "대통령실", row: 2 },

            // 3열: 국무위원
            { name: "윤재순", role1: "내란선동자", role2: "총무비서관", group: "대통령실", row: 3 },
            { name: "김영호", role1: "내란방조자", role2: "통일부장관", group: "대통령실", row: 3 },
            { name: "송미령", role1: "내란방조자", role2: "농림축산식품부장관", group: "대통령실", row: 3 },
            { name: "조규홍", role1: "내란방조자", role2: "보건복지부장관", group: "대통령실", row: 3 },
            { name: "오영주", role1: "내란방조자", role2: "중기부장관", group: "대통령실", row: 3 },
            { name: "최상목", role1: "내란방조자", role2: "경제부총리", group: "대통령실", row: 3 },
            { name: "조태열", role1: "내란방조자", role2: "외교부장관", group: "대통령실", row: 3 },
            
            // 내란의힘
            { name: "추경호", role1: "내란주동자", role2: "대구 달성군", group: "내란의힘", row: 1 },
            { name: "권성동", role1: "내란동조자", role2: "강원 강릉시", group: "내란의힘", row: 1 },
            { name: "김석기", role1: "내란동조자", role2: "경북 경주시", group: "내란의힘", row: 1 },
            { name: "나경원", role1: "내란동조자", role2: "서울 동작구", group: "내란의힘", row: 1 },
            { name: "유상범", role1: "내란동조자", role2: "강원 홍천군횡성군영월군평창군", group: "내란의힘", row: 1 },
            { name: "유영하", role1: "내란동조자", role2: "대구 달서구갑", group: "내란의힘", row: 1 },
            { name: "윤상현", role1: "내란동조자", role2: "인천 동구미추홀구을", group: "내란의힘", row: 1 },
            { name: "윤한홍", role1: "내란동조자", role2: "경남 창원시마산회원구", group: "내란의힘", row: 1 },
            { name: "최형두", role1: "내란동조자", role2: "경남 창원시마산회원구", group: "내란의힘", row: 1 },
            { name: "강대식", role1: "내란동조자", role2: "대구 동구군위군을", group: "내란의힘", row: 1 },
            { name: "강명구", role1: "내란동조자", role2: "경북 구미시을", group: "내란의힘", row: 1 },
            { name: "강민국", role1: "내란동조자", role2: "경남 진주시을", group: "내란의힘", row: 1 },
            { name: "강선영", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "강승규", role1: "내란동조자", role2: "충남 홍성군예산군", group: "내란의힘", row: 1 },
            { name: "고동진", role1: "내란동조자", role2: "서울 강남구병", group: "내란의힘", row: 1 },
            { name: "구자근", role1: "내란동조자", role2: "경북 구미시갑", group: "내란의힘", row: 1 },
            { name: "권영세", role1: "내란동조자", role2: "서울 용산구", group: "내란의힘", row: 1 },
            { name: "권영진", role1: "내란동조자", role2: "대구 달서구병", group: "내란의힘", row: 1 },
            { name: "김건", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "김기웅", role1: "내란동조자", role2: "대구 중구남구", group: "내란의힘", row: 1 },
            { name: "김기현", role1: "내란동조자", role2: "울산 남구을", group: "내란의힘", row: 1 },
            { name: "김대식", role1: "내란동조자", role2: "부산 사상구", group: "내란의힘", row: 1 },
            { name: "김도읍", role1: "내란동조자", role2: "부산 강서구", group: "내란의힘", row: 1 },
            { name: "김미애", role1: "내란동조자", role2: "부산 해운대구을", group: "내란의힘", row: 1 },
            { name: "김민전", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "김상훈", role1: "내란동조자", role2: "대구 서구", group: "내란의힘", row: 1 },
            { name: "김선교", role1: "내란동조자", role2: "경기 여주시양평군", group: "내란의힘", row: 1 },
            { name: "김소희", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "김승수", role1: "내란동조자", role2: "대구 북구을", group: "내란의힘", row: 1 },
            { name: "김위상", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "김은혜", role1: "내란동조자", role2: "경기 성남시분당구을", group: "내란의힘", row: 1 },
            { name: "김장겸", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "김정재", role1: "내란동조자", role2: "경북 포항시북구", group: "내란의힘", row: 1 },
            { name: "김종양", role1: "내란동조자", role2: "경남 창원시의창구", group: "내란의힘", row: 1 },
            { name: "김태호", role1: "내란동조자", role2: "경남 양산시을", group: "내란의힘", row: 1 },
            { name: "김희정", role1: "내란동조자", role2: "부산 연제구", group: "내란의힘", row: 1 },
            { name: "박대출", role1: "내란동조자", role2: "경남 진주시갑", group: "내란의힘", row: 1 },
            { name: "박덕흠", role1: "내란동조자", role2: "충남 보령시서천군", group: "내란의힘", row: 1 },
            { name: "박상웅", role1: "내란동조자", role2: "경남 밀양시의령군함안군창녕군", group: "내란의힘", row: 1 },
            { name: "박성민", role1: "내란동조자", role2: "울산 중구", group: "내란의힘", row: 1 },
            { name: "박성훈", role1: "내란동조자", role2: "부산 북구을", group: "내란의힘", row: 1 },
            { name: "박수영", role1: "내란동조자", role2: "부산 남구", group: "내란의힘", row: 1 },
            { name: "박준태", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "박충권", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "박형수", role1: "내란동조자", role2: "경북 의성군청송군영덕군울진군", group: "내란의힘", row: 1 },
            { name: "배준영", role1: "내란동조자", role2: "인천 중구강화군옹진군", group: "내란의힘", row: 1 },
            { name: "배현진", role1: "내란동조자", role2: "서울 송파구을", group: "내란의힘", row: 1 },
            { name: "백종헌", role1: "내란동조자", role2: "부산 금정구", group: "내란의힘", row: 1 },
            { name: "서명옥", role1: "내란동조자", role2: "서울 강남구갑", group: "내란의힘", row: 1 },
            { name: "서일준", role1: "내란동조자", role2: "경남 거제시", group: "내란의힘", row: 1 },
            { name: "서지영", role1: "내란동조자", role2: "부산 동래구", group: "내란의힘", row: 1 },
            { name: "서천호", role1: "내란동조자", role2: "경남 사천시남해군하동군", group: "내란의힘", row: 1 },
            { name: "성일종", role1: "내란동조자", role2: "충남 서산시태안군", group: "내란의힘", row: 1 },
            { name: "송석준", role1: "내란동조자", role2: "경기 이천시", group: "내란의힘", row: 1 },
            { name: "송언석", role1: "내란동조자", role2: "경북 김천시", group: "내란의힘", row: 1 },
            { name: "신동욱", role1: "내란동조자", role2: "서울 서초구을", group: "내란의힘", row: 1 },
            { name: "안상훈", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "엄태영", role1: "내란동조자", role2: "충북 제천시단양군", group: "내란의힘", row: 1 },
            { name: "유용원", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "윤영석", role1: "내란동조자", role2: "경남 양산시갑", group: "내란의힘", row: 1 },
            { name: "윤재옥", role1: "내란동조자", role2: "대구 달서구을", group: "내란의힘", row: 1 },
            { name: "이달희", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "이만희", role1: "내란동조자", role2: "경북 영천시예천군", group: "내란의힘", row: 1 },
            { name: "이상휘", role1: "내란동조자", role2: "경북 포항시남구울릉군", group: "내란의힘", row: 1 },
            { name: "이성권", role1: "내란동조자", role2: "부산 사하구갑", group: "내란의힘", row: 1 },
            { name: "이양수", role1: "내란동조자", role2: "강원 속초시인제군고성군양양군", group: "내란의힘", row: 1 },
            { name: "이인선", role1: "내란동조자", role2: "대구 수성구을", group: "내란의힘", row: 1 },
            { name: "이종배", role1: "내란동조자", role2: "충북 충주시", group: "내란의힘", row: 1 },
            { name: "이종욱", role1: "내란동조자", role2: "경남 창원시진해구", group: "내란의힘", row: 1 },
            { name: "이철규", role1: "내란동조자", role2: "강원 동해시태백시삼척시정선군", group: "내란의힘", row: 1 },
            { name: "이헌승", role1: "내란동조자", role2: "부산 부산진구을", group: "내란의힘", row: 1 },
            { name: "인요한", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "임이자", role1: "내란동조자", role2: "경북 상주시문경시", group: "내란의힘", row: 1 },
            { name: "임종득", role1: "내란동조자", role2: "경북 영주시영양군봉화군", group: "내란의힘", row: 1 },
            { name: "정동만", role1: "내란동조자", role2: "부산 기장군", group: "내란의힘", row: 1 },
            { name: "정점식", role1: "내란동조자", role2: "경남 통영시고성군", group: "내란의힘", row: 1 },
            { name: "정희용", role1: "내란동조자", role2: "경북 고령군성주군칠곡군", group: "내란의힘", row: 1 },
            { name: "조배숙", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "조승환", role1: "내란동조자", role2: "부산 중구영도구", group: "내란의힘", row: 1 },
            { name: "조은희", role1: "내란동조자", role2: "서울 서초구갑", group: "내란의힘", row: 1 },
            { name: "조정훈", role1: "내란동조자", role2: "서울 마포구갑", group: "내란의힘", row: 1 },
            { name: "조지연", role1: "내란동조자", role2: "경북 경산시", group: "내란의힘", row: 1 },
            { name: "주호영", role1: "내란동조자", role2: "대구 수성구갑", group: "내란의힘", row: 1 },
            { name: "진종오", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "최보윤", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "최수진", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row: 1 },
            { name: "최은석", role1: "내란동조자", role2: "대구 동구군위군갑", group: "내란의힘", row: 1 },
            { name: "한기호", role1: "내란동조자", role2: "강원 춘천시철원군화천군양구군을", group: "내란의힘", row: 1 },
            { name: "곽규택", role1: "내란동조자", role2: "부산 서구동구", group: "내란의힘", row: 2 },
            { name: "김상욱", role1: "내란동조자", role2: "울산 남구갑", group: "내란의힘", row: 2 },
            { name: "김성원", role1: "내란동조자", role2: "경기 동두천시양주시연천구을", group: "내란의힘", row: 2 },
            { name: "김용태", role1: "내란동조자", role2: "경기 포천시가평군", group: "내란의힘", row: 2 },
            { name: "김재섭", role1: "내란동조자", role2: "서울 도봉구갑", group: "내란의힘", row: 2 },
            { name: "김형동", role1: "내란동조자", role2: "경북 안동시예천군", group: "내란의힘", row: 2 },
            { name: "박수민", role1: "내란동조자", role2: "서울 강남구을", group: "내란의힘", row: 2 },
            { name: "박정하", role1: "내란동조자", role2: "강원 강릉시", group: "내란의힘", row: 2 },
            { name: "박정훈", role1: "내란동조자", role2: "서울 송파구갑", group: "내란의힘", row: 2 },
            { name: "서범수", role1: "내란동조자", role2: "울산 울주군", group: "내란의힘", row: 2 },
            { name: "신성범", role1: "내란동조자", role2: "경남 산청군함양군거창군합천군", group: "내란의힘", row: 2 },
            { name: "우재준", role1: "내란동조자", role2: "대구 북구갑", group: "내란의힘", row: 2 },
            { name: "장동혁", role1: "내란동조자", role2: "충남 보령시서천군", group: "내란의힘", row: 2 },
            { name: "정성국", role1: "내란동조자", role2: "부산 부산진구을", group: "내란의힘", row: 2 },
            { name: "정연욱", role1: "내란동조자", role2: "부산 수영구", group: "내란의힘", row: 2 },
            { name: "조경태", role1: "내란동조자", role2: "부산 사하구을", group: "내란의힘", row: 2 },
            { name: "주진우", role1: "내란동조자", role2: "부산 해운대구갑", group: "내란의힘", row: 2 },
            { name: "한지아", role1: "내란동조자", role2: "비례대표", group: "내란의힘", row : 2 },

            { name: "한동훈", role1: "혼동훈", role2: "한미꾸라지", group: "내란의힘", row: 2 },
            { name: "홍준표", role1: "내란선동자", role2: "대구시장", group: "내란의힘", row: 2 },
            { name: "황교안", role1: "내란선동자", role2: "유튜버", group: "내란의힘", row: 2 },
            { name: "선주헌", role1: "내란선동자", role2: "영월군의원 나", group: "내란의힘", row: 2 },


            // 기타·극우미디어
            { name: "양태석", role1: "내란선동자", role2: "거제시의원 가선거구", group: "기타·극우미디어", row: 3 },
            { name: "채일", role1: "내란선동자", role2: "국방부홍보원장", group: "기타·극우미디어", row: 3 },
            { name: "전원책", role1: "내란선동자", role2: "변호사", group: "기타·극우미디어", row: 3 }
        ];

        // 카드 생성 함수
        function createPersonCard(person) {
            const card = document.createElement('div');
            card.className = 'person-container';
            card.setAttribute('data-name', person.name.toLowerCase());
            card.setAttribute('data-role1', person.role1.toLowerCase());
            card.setAttribute('data-role2', person.role2.toLowerCase());
            
            // 이미지 생성
            const img = document.createElement('img');
            const groupFolder = person.group;
            img.src = `images/${groupFolder}/${person.name}.jpeg`;
            img.alt = person.name;
            
            // 이미지 로드 실패시 .jpg 확장자로 재시도, 그래도 실패하면 대체 이미지 사용
            img.onerror = function() {
                if (this.src.endsWith('.jpeg')) {
                    this.src = `images/${groupFolder}/${person.name}.jpg`;
                } else {
                    this.src = `images/${groupFolder}/${groupFolder}.jpeg`;
                }
            };

            // 이름과 역할 정보
            const name = document.createElement('div');
            name.className = 'person-name';
            name.textContent = person.name;

            const role1 = document.createElement('div');
            role1.className = 'person-role';
            role1.textContent = person.role1;

            const role2 = document.createElement('div');
            role2.className = 'person-role2';
            role2.textContent = person.role2;

            // 요소들을 카드에 추가
            card.appendChild(img);
            card.appendChild(name);
            card.appendChild(role1);
            card.appendChild(role2);

            // 클릭 이벤트 추가
            card.addEventListener('click', function() {
                const modal = document.getElementById('personModal');
                const modalImage = document.getElementById('modalImage');
                const modalName = document.getElementById('modalName');
                const modalRole1 = document.getElementById('modalRole1');
                const modalRole2 = document.getElementById('modalRole2');
                const modalActions = document.getElementById('modalActions');
                const modalActionsView = document.getElementById('modalActionsView');

                modalImage.src = img.src;
                modalName.textContent = person.name;
                modalRole1.textContent = person.role1;
                modalRole2.textContent = person.role2;
                
                const actions = person.actions || '';
                modalActions.value = actions;
                modalActionsView.innerHTML = formatActions(actions);

                // 관리자 상태에 따라 UI 조정
                document.getElementById('adminLoginBtn').style.display = isAdmin ? 'none' : 'inline-block';
                document.getElementById('saveBtn').style.display = isAdmin ? 'inline-block' : 'none';
                document.getElementById('modalActions').style.display = isAdmin ? 'block' : 'none';

                modal.style.display = 'block';
            });

            return card;
        }

        // 사람들 렌더링 함수
        function renderPeople() {
            const groupedPeople = {};
            people.forEach(person => {
                if (!groupedPeople[person.group]) {
                    groupedPeople[person.group] = [];
                }
                groupedPeople[person.group].push(person);
            });

            Object.keys(groupedPeople).forEach(group => {
                const container = document.getElementById(`${group}-container`);
                if (container) {
                    container.innerHTML = '';
                    
                    if (group === '내란수괴') {
                        const rowDiv = document.createElement('div');
                        rowDiv.style.display = 'flex';
                        rowDiv.style.justifyContent = 'center';
                        rowDiv.style.position = 'relative';
                        rowDiv.style.width = '100%';
                        
                        groupedPeople[group].forEach(person => {
                            const card = createPersonCard(person);
                            if (person.position === 'center') {
                                card.style.margin = '0 auto';
                            } else if (person.position === 'right') {
                                card.style.position = 'absolute';
                                card.style.right = '0';
                                card.style.top = '0';
                            }
                            rowDiv.appendChild(card);
                        });
                        
                        container.appendChild(rowDiv);
                    } else if (group === '내란의힘') {
                        let martialLawPeople = [];
                        let martialLawAgreePeople = [];
                        let otherPeople = [];
                        let isInMartialLawGroup = false;
                        let isInMartialLawAgreeGroup = false;
                        
                        groupedPeople[group].forEach(person => {
                            if (person.name === '추경호') {
                                isInMartialLawGroup = true;
                            } else if (person.name === '곽규택') {
                                isInMartialLawAgreeGroup = true;
                            }
                            
                            if (isInMartialLawGroup) {
                                martialLawPeople.push(person);
                            } else if (isInMartialLawAgreeGroup) {
                                martialLawAgreePeople.push(person);
                            } else {
                                otherPeople.push(person);
                            }
                            
                            if (person.name === '한기호') {
                                isInMartialLawGroup = false;
                            } else if (person.name === '한지아') {
                                isInMartialLawAgreeGroup = false;
                            }
                        });
                        
                        // 계엄해제 불참자 그룹 먼저 렌더링
                        const martialLawGroup = document.createElement('div');
                        martialLawGroup.className = 'martial-law-group';
                        const martialLawContainer = document.createElement('div');
                        martialLawContainer.className = 'people-container';
                        martialLawGroup.appendChild(martialLawContainer);
                        
                        martialLawPeople.forEach(person => {
                            martialLawContainer.appendChild(createPersonCard(person));
                        });
                        container.appendChild(martialLawGroup);
                        
                        // 계엄해제 동의자 그룹 렌더링
                        const martialLawAgreeGroup = document.createElement('div');
                        martialLawAgreeGroup.className = 'martial-law-agree-group';
                        const martialLawAgreeContainer = document.createElement('div');
                        martialLawAgreeContainer.className = 'people-container';
                        martialLawAgreeGroup.appendChild(martialLawAgreeContainer);
                        
                        martialLawAgreePeople.forEach(person => {
                            martialLawAgreeContainer.appendChild(createPersonCard(person));
                        });
                        container.appendChild(martialLawAgreeGroup);
                        
                        // 나머지 인물들 렌더링
                        otherPeople.forEach(person => {
                            container.appendChild(createPersonCard(person));
                        });
                    } else {
                        // row 별로 정렬
                        const rowGroups = {};
                        groupedPeople[group].forEach(person => {
                            if (!rowGroups[person.row]) {
                                rowGroups[person.row] = [];
                            }
                            rowGroups[person.row].push(person);
                        });

                        // 각 row 렌더링
                        Object.keys(rowGroups).sort().forEach(rowNum => {
                            const rowDiv = document.createElement('div');
                            rowDiv.className = 'row';
                            rowGroups[rowNum].forEach(person => {
                                rowDiv.appendChild(createPersonCard(person));
                            });
                            container.appendChild(rowDiv);
                        });
                    }
                }
            });
        }

        // 검색 기능
        function setupSearch() {
            const searchInput = document.getElementById('searchInput');
            const searchResults = document.querySelector('.search-results');
            
            // 이전 하이라이트 효과 제거 함수
            function removeHighlights() {
                const allCards = document.querySelectorAll('.person-container');
                allCards.forEach(card => {
                    card.style.animation = '';
                    card.style.opacity = '1';
                });
            }

            // 카드로 스크롤 및 하이라이트 효과 적용
            function scrollToCard(matchingCard) {
                if (!matchingCard) return;

                removeHighlights();

                matchingCard.scrollIntoView({
                    behavior: 'smooth',
                    block: 'center'
                });
                
                matchingCard.style.animation = 'highlight 2s';
                matchingCard.style.opacity = '1';

                const allCards = document.querySelectorAll('.person-container');
                allCards.forEach(card => {
                    if (card !== matchingCard) {
                        card.style.opacity = '0.5';
                    }
                });

                setTimeout(() => {
                    allCards.forEach(card => {
                        card.style.opacity = '1';
                    });
                }, 3000);
            }

            // 실시간 검색 결과 표시
            searchInput.addEventListener('input', function() {
                const searchTerm = this.value.trim().toLowerCase();
                
                if (searchTerm.length < 1) {
                    searchResults.style.display = 'none';
                    return;
                }

                // people 배열에서 검색
                const matchingPeople = [];
                Object.keys(people).forEach(category => {
                    people[category].forEach(person => {
                        if (person.name.toLowerCase().includes(searchTerm) ||
                            person.role1.toLowerCase().includes(searchTerm) ||
                            person.role2.toLowerCase().includes(searchTerm)) {
                            matchingPeople.push({
                                ...person,
                                category: category
                            });
                        }
                    });
                });

                if (matchingPeople.length > 0) {
                    searchResults.innerHTML = matchingPeople.map(person => `
                        <div class="search-result-item" data-name="${person.name}">
                            <div class="search-result-name">${person.name}</div>
                            <div class="search-result-role">
                                <span class="search-result-category">${person.category}</span>
                                ${person.role1}${person.role2 ? ` | ${person.role2}` : ''}
                            </div>
                        </div>
                    `).join('');
                    searchResults.style.display = 'block';
                } else {
                    searchResults.style.display = 'none';
                }
            });

            // 검색 결과 클릭 이벤트
            searchResults.addEventListener('click', function(e) {
                const resultItem = e.target.closest('.search-result-item');
                if (!resultItem) return;

                const name = resultItem.dataset.name;
                const matchingCard = document.querySelector(`.person-container[data-name="${name.toLowerCase()}"]`);
                
                searchInput.value = '';
                searchResults.style.display = 'none';
                scrollToCard(matchingCard);
            });

            // 엔터키 검색
            searchInput.addEventListener('keyup', function(e) {
                if (e.key === 'Enter') {
                    const searchTerm = this.value.trim().toLowerCase();
                    const matchingCard = document.querySelector(`.person-container[data-name*="${searchTerm}"]`);
                    
                    searchResults.style.display = 'none';
                    scrollToCard(matchingCard);
                }
            });

            // 검색창 외부 클릭시 결과 숨기기
            document.addEventListener('click', function(e) {
                if (!e.target.closest('.search-container')) {
                    searchResults.style.display = 'none';
                }
            });
        }

        // 위로 가기 버튼 기능
        function setupScrollTopButton() {
            const scrollTopBtn = document.querySelector('.scroll-top-btn');
            scrollTopBtn.addEventListener('click', function() {
                window.scrollTo({
                    top: 0,
                    behavior: 'smooth'
                });
            });
        }

        // 모달 창 기능
        function setupModal() {
            const modal = document.getElementById('personModal');
            const adminModal = document.getElementById('adminModal');
            const modalClose = modal.querySelector('.modal-close');
            const adminModalClose = adminModal.querySelector('.modal-close');
            const modalActions = document.getElementById('modalActions');
            const modalActionsView = document.getElementById('modalActionsView');
            const adminLoginBtn = document.getElementById('adminLoginBtn');
            const saveBtn = document.getElementById('saveBtn');

            // 관리자 로그인 버튼 클릭
            adminLoginBtn.addEventListener('click', function() {
                adminModal.style.display = 'block';
            });

            // 모달 창 닫기
            modalClose.addEventListener('click', function() {
                modal.style.display = 'none';
            });

            adminModalClose.addEventListener('click', function() {
                adminModal.style.display = 'none';
            });

            // 모달 창 외부 클릭시 닫기
            window.addEventListener('click', function(e) {
                if (e.target === modal) {
                    modal.style.display = 'none';
                }
                if (e.target === adminModal) {
                    adminModal.style.display = 'none';
                }
            });

            // 저장 버튼 클릭 시
            saveBtn.addEventListener('click', function() {
                if (!isAdmin) return;
                
                const personName = document.getElementById('modalName').textContent;
                const actions = modalActions.value;

                // people 배열에서 해당 인물 찾기
                const person = people.find(p => p.name === personName);
                if (person) {
                    person.actions = actions;
                    // localStorage에 저장
                    const savedActions = JSON.parse(localStorage.getItem('personActions') || '{}');
                    savedActions[personName] = actions;
                    localStorage.setItem('personActions', JSON.stringify(savedActions));
                    
                    // 뷰 업데이트
                    modalActionsView.innerHTML = formatActions(actions);

                    modal.style.display = 'none';
                }
            });

            // 저장된 행적 불러오기
            const savedActions = JSON.parse(localStorage.getItem('personActions') || '{}');
            people.forEach(person => {
                if (savedActions[person.name]) {
                    person.actions = savedActions[person.name];
                }
            });
        }

        // 관리자 비밀번호 확인
        function checkAdminPassword() {
            const password = document.getElementById('adminPassword').value;
            if (password === ADMIN_PASSWORD) {
                isAdmin = true;
                document.getElementById('adminModal').style.display = 'none';
                document.getElementById('adminLoginBtn').style.display = 'none';
                document.getElementById('saveBtn').style.display = 'inline-block';
                document.getElementById('modalActions').style.display = 'block';
            } else {
                alert('비밀번호가 올바르지 않습니다.');
            }
        }

        // 행적 텍스트 포맷팅
        function formatActions(actions) {
            if (!actions || actions.trim() === '') {
                return '<p class="pending-message">곧 업데이트 하겠습니다..</p>';
            }
            return `<p class="actions-text">${actions.replace(/\n/g, '<br>')}</p>`;
        }

        // 관리자 모드 관련 변수
        let isAdmin = false;
        const ADMIN_PASSWORD = '03122024'; 

        // 공지사항 관련 함수
        function showNotice() {
            document.getElementById('noticeModal').style.display = 'block';
        }

        function closeNotice() {
            document.getElementById('noticeModal').style.display = 'none';
        }

        // 페이지 로드시 공지사항 표시
        window.onload = function() {
            showNotice();
        };

        // 페이지 로드시 실행
        document.addEventListener('DOMContentLoaded', function() {
            renderPeople();
            setupSearch();
            setupScrollTopButton();
            setupModal();
        });
    </script>
</body>
</html>
