l. quick way to create Github Actions workflow use starter workflows. https://docs.github.com/en/actions/learn-github-actions/using-starter-workflows
2. CI workflows to build and test code, https://docs.github.com/en/actions/automating-builds-and-tests
3. Build and publishing packages, https://docs.github.com/en/actions/publishing-packages
4. deploy project https://docs.github.com/en/actions/deployment
5. automating tasks and processes on GitHub, https://docs.github.com/en/actions/managing-issues-and-pull-requests

View examples: https://docs.github.com/en/actions/examples

Github action là CI/CD platform cho phép tự động hóa build, test deployment pipeline.
Github cung cấp Linux, Windows, macOS vm để run workflows. Có hỗ trợ self host runners.

# Thành Phần
- 1 hoặc nhiều job chạy tuần tự hoặc đồng thời.
- mỗi job sẽ chạy bên trong vm runner nó sở hữu, hoặc trong container.
- 1 hoặc nhiều steps chạy script được định nghĩa. hoặc chạy một action.

![Alt text](image.png)

## 1. Workflows
Được đinh nghĩa trong .github/workflows directory của repository, có thể có nhiều workflows trên 1 repo, mỗi cái thực hiện tập hợp các task khác nhau.

## 2. Events
1 hành động cụ thể trong repository triggers một workflow chạy. Có thể trigger workflow để chạy 1 schedule, bằng post đến 1 REST API hoặc manually.

## 3. Jobs
Tập hợp các steps trong workflow mà được thực hiện trên cùng runner. Mỗi steps hoặc là một shell script hoặc một hành động sẽ chạy. Các step được thực hiện theo trình tự và phụ thộc vào những cái khác. Steps cùng runner có thể chia sẽ dữ liệu với nhau.

Có thể cấu hình job depen trên job khác, mặc định thì nó không dependen và run đồng thời với những cái khác. Khi 1 job phụ thuộc cía khác thì nó sẽ đợi job complete trước khi nó chạy. 

## 4. Actions
Custom application cho Github Action thực hiện nhiệm vụ phức tạp lặp đi lặp lại. Giảm đi lượng code lặp lại khi viêt workflow. 
Có thể pull code từ repository, thiết lập các công cụ cho môi trường build hoặc setup authentication cho cloud provider.

# 5. Runners
1 máy chủ chạy workflow khi được trigger. 