GitHub Actions에 워크플로우를 작성해 다음과 같이 배포가 진행되도록 함
<img width="825" alt="스크린샷 2024-07-26 오전 8 44 33" src="https://github.com/user-attachments/assets/907d55ac-69b8-4fd3-8d26-7214b4077408">
1. 저장소를 체크아웃합니다.
2. Node.js 18.x 버전을 설정합니다.
3. 프로젝트 의존성을 설치합니다.
4. Next.js 프로젝트를 빌드합니다.
5. AWS 자격 증명을 구성합니다.
6. 빌드된 파일을 S3 버킷에 동기화합니다.
7. CloudFront 캐시를 무효화합니다.


## 주요 링크

- S3 버킷 웹사이트 엔드포인트: [http://hanghae.s3-website-ap-southeast-2.amazonaws.com](http://hanghae.s3-website-ap-southeast-2.amazonaws.com)
- CloudFrount 배포 도메인 이름: [https://d1c6e2953k885f.cloudfront.net](https://d1c6e2953k885f.cloudfront.net)

## 주요 개념

- GitHub Actions과 CI/CD 도구:
GitHub Actions은 소프트웨어 개발 워크플로우를 자동화할 수 있는 CI/CD(지속적 통합/지속적 배포) 플랫폼입니다. 코드 변경 사항을 자동으로 빌드, 테스트, 배포할 수 있어 개발 프로세스를 효율적으로 만들어줍니다.
- S3와 스토리지:
Amazon S3(Simple Storage Service)는 확장 가능한 클라우드 스토리지 서비스입니다. 웹사이트 호스팅, 백업, 아카이브 등 다양한 용도로 사용할 수 있으며, 프론트엔드 프로젝트의 정적 파일을 저장하고 제공하는 데 적합합니다.
- CloudFront와 CDN:
Amazon CloudFront는 콘텐츠 전송 네트워크(CDN) 서비스입니다. 전 세계에 분산된 엣지 로케이션을 통해 콘텐츠를 사용자와 가까운 위치에서 제공함으로써 웹사이트의 성능과 로딩 속도를 향상시킵니다.
- 캐시 무효화(Cache Invalidation):
캐시 무효화는 CDN의 캐시된 콘텐츠를 강제로 업데이트하는 프로세스입니다. 웹사이트 콘텐츠가 변경되었을 때 CloudFront의 엣지 로케이션에 저장된 이전 버전의 캐시를 제거하고 최신 버전으로 업데이트하는 데 사용됩니다.
- Repository secret과 환경변수:
GitHub의 Repository secrets는 민감한 정보(예: API 키, 액세스 토큰)를 안전하게 저장하고 관리하는 기능입니다. 이 비밀값들은 GitHub Actions 워크플로우에서 환경 변수로 사용될 수 있으며, 코드에 직접 노출시키지 않고 안전하게 프로젝트에서 사용할 수 있습니다.
