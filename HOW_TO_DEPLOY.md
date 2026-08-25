# 🚀 GitHub Pages 배포 가이드

Kim Kyung Dong (김경동) - Academic CV Website
Based on al-folio Jekyll theme

---

## 📌 최종 접속 URL

배포 완료 후: **https://kkyungdong.github.io/CV/**

---

## 1단계: 파일 업로드

### 방법 A) GitHub 웹에서 직접 업로드 (가장 쉬움)

1. https://github.com/kkyungdong/CV 접속
2. 화면의 **"uploading an existing file"** 링크 클릭
3. 이 폴더 안의 **모든 파일과 폴더**를 드래그 앤 드롭
   - `_config.yml`, `_pages/`, `_bibliography/`, `_data/`, `assets/`, `Gemfile` 등 모두
4. 하단 커밋 메시지: `Initial CV site deployment`
5. **Commit changes** 클릭

⚠️ 폴더가 너무 많아서 웹 업로드가 오래 걸리면 방법 B 권장

### 방법 B) Git 명령어로 업로드 (더 안정적)

```bash
# 이 폴더에서 실행
cd al-folio-build

git init
git add .
git commit -m "Initial CV site deployment"
git branch -M main
git remote add origin https://github.com/kkyungdong/CV.git
git push -u origin main
```

---

## 2단계: GitHub Pages 활성화

1. https://github.com/kkyungdong/CV/settings/pages 접속
2. **Build and deployment** 섹션에서:
   - Source: **GitHub Actions** 선택 (al-folio는 Actions 방식 권장)
3. 저장하면 자동으로 배포 워크플로가 실행됨
4. **Actions** 탭에서 빌드 진행 상황 확인 (3~5분 소요)
5. 완료되면 **https://kkyungdong.github.io/CV/** 접속 🎉

---

## 3단계: 프로필 사진 교체

기본 자리표시자 이미지가 `assets/img/prof_pic.jpg`에 있어요.
본인 사진으로 교체하려면:

1. https://github.com/kkyungdong/CV/blob/main/assets/img/prof_pic.jpg 접속
2. 우측 상단 연필 아이콘 옆 **"Delete file"** 아이콘 클릭
3. 다시 `assets/img/` 폴더에서 **Add file → Upload files**
4. 본인 사진을 `prof_pic.jpg` 이름으로 업로드
5. 커밋 → 자동으로 사이트에 반영됨

---

## 📝 앞으로 콘텐츠 편집하기

### 새 논문 추가
`_bibliography/papers.bib` 파일 편집:
```bibtex
@article{kim2027example,
  title     = {새 논문 제목},
  author    = {Kim, Kyungdong and ...},
  journal   = {저널명},
  year      = {2027},
  selected  = {true}
}
```

### 자기소개 수정
`_pages/about.md` 편집

### CV 이력 업데이트
`_pages/cv.md` 또는 `_data/cv.yml` 편집

### 프로젝트 추가/수정
`_pages/projects.md` 편집

---

## 🐛 문제 해결

### 사이트가 안 뜰 때
- Settings → Pages 에서 Source가 **GitHub Actions**인지 확인
- Actions 탭에서 빌드 에러 확인
- `_config.yml`의 `baseurl: /CV`가 그대로인지 확인

### 이미지가 안 보일 때
- 이미지 경로는 항상 `/assets/img/파일명` 형태로
- 대소문자 정확히 일치해야 함

### 이메일 안 나올 때
- `_data/socials.yml`에 `email: kyungdong@snu.ac.kr` 확인

---

## 📚 참고 자료

- al-folio 공식 문서: https://github.com/alshedivat/al-folio
- Jekyll 문서: https://jekyllrb.com/docs/
- GitHub Pages: https://docs.github.com/en/pages

---

**Last prepared: 2026-08-25**
