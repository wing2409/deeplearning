한국어 Word2Vec 만들기(참고 : https://wikidocs.net/22660)

    (1) 훈련 데이터 생성
        1. 위키피디아 한국어 덤프 파일 다운로드
            1) url : https://dumps.wikimedia.org/kowiki/latest/
            2) 데이터 중 kowiki-latest-pages-articles.xml.bz2 다운로드

        2. 위키피디아 익스트랙터 다운로드
            1) url : https://github.com/attardi/wikiextractor
            2) zip 다운로드 후 압축 해제

        3. 위키피디아 한국어 덤프 파일 변환
            1) wikiextractor 압축 해제 디렉터리 이동
            2) 1.에서 다운 받은 kowiki-latest-pages-articles.xml.bz2를 같은 경로의 디렉터리로 복사
            3) 해당 명령어 실행 python WikiExtractor.py kowiki-latest-pages-articles.xml.bz2
            4) text폴더가 만들어졌고 폴더 안에 AA ~ AF 안의 모든 wiki00 ~ wiki90 데이터 생성

         4. 훈련 데이터 만들기
            1) 3.에서 만들어진 AA ~ AF 안의 모든 wiki00 ~ wiki90를 하나의 txt파일로 만듬
            2) copy AA디렉토리의 경로\wiki* wikiAA.txt
               copy AB디렉토리의 경로\wiki* wikiAB.txt
               copy AC디렉토리의 경로\wiki* wikiAC.txt
               copy AD디렉토리의 경로\wiki* wikiAD.txt
               copy AE디렉토리의 경로\wiki* wikiAE.txt
               copy AF디렉토리의 경로\wiki* wikiAF.txt
            3) copy 현재 디렉토리의 경로\wikiA* wiki_data.txt


    (2) konlpy install(참고 : https://konlpy-ko.readthedocs.io/ko/v0.4.3/install/)
        1. jva 1.7 이상 jdk 설치(jdk 1.8 : https://www.oracle.com/technetwork/java/javase/downloads/java-archive-javase8-2177648.html)
            1) java 설치
            2) java 환경변수 설정(제어판->시스템 및 보안->시스템->고급 시스템 설정->환경변수 클릭)
            3) 시스템 변수 새로 만들기 클릭(변수명 : JAVA_PATH, 변수 값 : C:\경로\jdk1.8.0_211)
            4) 변수명 Path 더블 클릭 새로 만들기(C:\경로\jdk1.8.0_211\bin)

        2. JPype1 다운로드(https://www.lfd.uci.edu/~gohlke/pythonlibs/#jpype)
            1) python 버젼이 3.6이면 JPype1‑0.6.3‑cp36‑cp36m‑win_amd64.whl, 3.7이면 JPype1‑0.6.3‑cp37‑cp37m‑win_amd64.whl 다운로드
            2) 다운로드 받은 경로에서
                > pip install --upgrade pip
                > pip install JPype1‑0.6.3‑cp36‑cp36m‑win_amd64.whl (파일명이 다를수도 있음!)

        3. 명령 프롬프트로 KoNLPy 설치하기
            1) pip install konlpy
