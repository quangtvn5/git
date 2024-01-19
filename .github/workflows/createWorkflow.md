Mỗi workflow được chứa riêng biệt trong code repository, trong .github/workflows.
```
name: learn-github-actions
run-name: ${{ github.actor }} is learning GitHub Actions
on: [push]
jobs:
  check-bats-version:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v3
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```
name: tên của workflow sẽ xuất hiện trong Actions tab.

run-name: tên cho workflow runs được tạo từ workflow, cái sẽ xuất hiện trong danh sách workflows chạy trên repository actions tab.

on:  xác định trigger cho workflow.

jobs: nhóm tất cả các job chạy trong workflow.

check-bats-version: định nghĩa job name.
