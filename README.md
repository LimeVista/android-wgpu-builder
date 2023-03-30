# Android Web GPU Builder
[wgpu](https://github.com/gfx-rs/wgpu) Android AAR Builder

## 环境（Environment）
* Android SDK 23+
* arm64、x86_64
* Android Studio 4.1.+

## 使用（Usage）

* 添加源（add repository）
```groovy
allprojects {
  repositories {
    // ...
    maven { url "https://raw.githubusercontent.com/LimeVista/maven-repo/master/repos" }
  }
}
```

* 引入依赖
```groovy
dependencies {
    // ...
    implementation "me.limeice.android:wgpu:${ver}"
}
```

* 启用 prefab（Enable prefab）
```groovy
android {
    // ...
    buildFeatures {
        prefab true
    }
}
```

* 修改 `CMakeLists.txt` （Change `CMakeLists.txt`）
```cmake
find_package (wgpu REQUIRED CONFIG)

target_link_libraries(yourLib wgpu::wgpu android ${log-lib})
```