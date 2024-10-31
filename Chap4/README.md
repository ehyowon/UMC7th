Spring MVC패턴 적용하여 간단한 게시판(CRUD 기능) api서버 구현해보기

### Post
게시글 객체 - id, title, content
- `id`: 게시글의 고유 번호
- `title`: 게시글 제목
- `content`: 게시글 내용

### PostRepository
게시글 데이터 목록 저장, 관리
- `findAll()`: 모든 게시글
- `findById(Long id)`: 특정 id에 해당하는 게시글
- `save(Post post)`: 새로운 게시글 저장하고, 고유한 id를 부여
- `deleteById(Long id)`: 특정 id에 해당하는 게시글 삭제

### PostService
PostRepository를 주입(@Autowired 또는 생성자 주입)
- `getAllPosts()`: 모든 게시글
- `getPostById(Long id)`: 특정 게시글 조회
- `createPost(String title, String content)`: 새로운 게시글 생성하여 저장
- `deletePost(Long id)`: 특정 게시글 삭제

### PostController
HTTP 요청을 받아서 PostService와 연동해 데이터 처리, 결과를 JSON 형식으로 응답
- `GET /api/posts`: 전체 게시글 목록
- `GET /api/posts/{id}`: 특정 게시글 조회
- `POST /api/posts`: 새 게시글 생성, 클라이언트가 JSON 형식으로 title과 content 전송
- `DELETE /api/posts/{id}`: 특정 게시글 삭제
