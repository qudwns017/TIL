# Reset

## reset
* git reset --(soft/mixed/hard) [commit hash]
* 이 모드는 커밋을 되돌리는 것은 아니며, 가장 최근 커밋부터 [commit hash]까지의 커밋 기록을 되돌리고, 그 이전의 모든 변경 내용을 스테이지(Staging Area)에 그대로 유지

### soft
```
git reset --soft [commit hash]
```
* 이 모드는 커밋을 되돌리는 것은 아니며, 가장 최근 커밋부터 [커밋 해시]까지의 커밋 기록을 되돌리고, 그 이전의 모든 변경 내용을 스테이징(Staging Area)에 그대로 유지합니다. 이후, 개발자는 변경 내용을 다시 수정하고, 커밋 재작성이 가능

### mixed
```
git reset --mixed [commit hash]
```
* 이 모드는 기본적으로 Soft 모드와 같은 동작을 수행하며, 추가로 스테이지에 추가한 변경 내용을 모두 되돌립니다.
* 가장 많이 사용되는 모드.

### hard
```
git reset --hard [commit hash]
```
* 이 모드는 모든 커밋과 스테이징을 commit hash 시점으로 되돌리고 그 사이의 내용들은 삭제해버림

## Reflog (Reference Log)
* Git의 내부 로그로, 로컬 저장소(Local Repository)에서 수행한 모든 작업(커밋, 브랜치 이동, 리셋 등)을 기록합니다.
* reflog는 로컬 저장소에서만 기록되며, 다른 개발자와 공유되지 않습니다