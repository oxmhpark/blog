---
title: Git：주요 메모
slug: git-주요-메모
excerpt: "저장소 관리 / 브랜치 관리 / 커밋·푸쉬 / 병합 / 기타"
date: 2025-03-27 03:14:09 +0900
years:
  - 2025
categories:
  - 개발일지
  - 관리
tags:
  - 깃
---
# 주요 명령어

## 저장소 관리

| 작업             | 명령                                    |
|------------------|-----------------------------------------|
| 저장소 초기화    | `git init`                              |
| 환경설정 보기    | `git config --list`                     |
| 환경설정 수정    | `git config --global KEY 'VALUE'`       |
| 원격 저장소 확인 | `git remote -v`                         |
| 원격 저장소 추가 | `git remote add REPO_NAME REPO_URL`     |
| 원격 저장소 변경 | `git remote set-url REPO_NAME REPO_URL` |
| 현재 브랜치 확인 | `git branch --show-current`             |
| 전체 브랜치 확인 | `git branch -a`                         |
| 로그 확인        | `git log [--oneline] [--graph] [--all]` |

## 브랜치 관리

| 작업                           | 명령                                       |
|--------------------------------|--------------------------------------------|
| 브랜치 생성 후 이동            | `git checkout -b BRANCH_NAME`              |
| 텅 빈 브랜치 생성 후 이동      | `git checkout --orphan BRANCH_NAME`        |
| (커밋 없이) 브랜치 이동        | `git switch BRANCH_NAME`                   |
| 로컬 브랜치 삭제               | `git branch [-d][-D] BRANCH_NAME`          |
| 원격 브랜치 삭제               | `git push REPO_NAME --delete BRANCH_NAME`  |
| 브랜치 업데이트 (현재)         | `git pull`                                 |
| 브랜치 업데이트 (특정)         | `git pull REPO_NAME BRANCH_NAME`           |
| 브랜치 업데이트 (Fast-forward) | `git pull --ff-only REPO_NAME BRANCH_NAME` |

## 커밋·푸쉬

| 작업                         | 명령                                          |
|------------------------------|-----------------------------------------------|
| 파일 추가                    | `git add PATH_TO_FILE`                        |
| 파일 추가 취소               | `git restore --staged PATH_TO_FILE`           |
| 커밋                         | `git commit -m 'MESSAGE'`                     |
| 로컬 커밋 수정               | `git commit --amend --no-edit`                |
| 로컬 커밋 수정 (메시지 갱신) | `git commit --amend -m 'MESSAGE'`             |
| 로컬 커밋 취소               | `git reset --soft HEAD~1`                     |
| 푸쉬                         | `git push REPO_NAME BRANCH_NAME`              |
| 푸쉬 취소                    | `git reset --hard HEAD~1 && git push --force` |
| 강제 푸쉬                    | `git push --force REPO_NAME BRANCH_NAME`      |

## 병합

| 작업                          | 명령                                                                   |
|-------------------------------|------------------------------------------------------------------------|
| 리베이스 (로컬)               | `git rebase BRANCH_NAME`                                               |
| 리베이스 (fetch+rebase)       | `git pull --rebase REPO_NAME BRANCH_NAME`                              |
| 중단된 리베이스 취소          | `git rebase --abort`                                                   |
| 중단된 리베이스 속행          | `git rebase --continue`                                                |
| 원격 변경사항 다운로드 (전체) | `git fetch REPO_NAME`                                                  |
| 원격 변경사항 다운로드 (특정) | `git fetch REPO_NAME BRANCH_NAME`                                      |
| 로컬 브랜치 병합              | `git merge BRANCH_NAME`                                                |
| 원격 브랜치 병합              | `git fetch REPO_NAME BRANCH_NAME`<br>`git merge REPO_NAME/BRANCH_NAME` |
| 충돌한 파일의 로컬 버전 유지  | `git restore --ours PATH_TO_FILE`                                      |
| 충돌한 파일의 원격 버전 유지  | `git restore --theirs PATH_TO_FILE`                                    |
| 병합 취소                     | `git merge --abort`                                                    |

## 기타

| 작업                           | 명령                          |
|--------------------------------|-------------------------------|
| 변경사항 임시저장              | `git stash`                   |
| 임시저장 목록 확인             | `git stash list`              |
| 마지막 임시저장 복원           | `git stash pop`               |
| 특정 임시저장 적용             | `git stash apply stash@{N}`   |
| 특정 임시저장 삭제             | `git stash drop stash@{N}`    |
| 모든 임시저장 삭제             | `git stash clear`             |
| 특정 커밋 되돌리기 (새로 커밋) | `git revert COMMIT_HASH`      |
| 특정 커밋 가져오기             | `git cherry-pick COMMIT_HASH` |
