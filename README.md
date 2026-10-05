# 算24点（安卓）

游戏本体是一个纯离线单文件网页 `app/src/main/assets/game24.html`；
安卓端是一个零第三方依赖的 WebView 壳。判定用精确分数，凑满 24 才算对。

## 方式一：想立刻玩（不用装任何东西）
把仓库外附带的 `game24.html` 传到手机，用浏览器打开即可；浏览器菜单里选「添加到主屏幕」，会像 App 一样在桌面有图标。

## 方式二：要 APK（云端免费打包，无需本地装 SDK）
1. 在 GitHub 新建一个仓库，把本文件夹内容全部上传（保持目录结构）。
2. 打开仓库的 Actions 页 → 左侧选「Build APK」→ Run workflow。
3. 等变绿后点进该次运行，页面底部 Artifacts 里下载 `game24-apk`，解压得到 `app-debug.apk`。
4. 传到手机安装（需允许「安装未知来源应用」）。

## 方式三：本地 Android Studio
Android Studio → Open 本文件夹 → 选一台真机/模拟器 Run；或 Build → Build APK(s)。
（首次打开会让 Gradle 联网同步一次，属正常现象。）

## 说明
- `app-debug.apk` 是调试签名，仅自用；上架需 Build → Generate Signed Bundle / APK 做正式签名。
- 工程 minSdk 24（Android 7.0+），compile/target 34，Java 17，无任何第三方库。
