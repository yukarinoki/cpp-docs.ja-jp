---
title: CppProperties.json スキーマ リファレンス
ms.date: 03/21/2019
helpviewer_keywords:
- CMake in Visual C++
ms.openlocfilehash: 43ffa0e92649fe233c6a743d4b64a2749cb28f5a
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341643"
---
# <a name="cpppropertiesjson-schema-reference"></a>CppProperties.json スキーマ リファレンス

CMake を使用していない "フォルダーを開く" プロジェクトでは、`CppProperties.json` ファイルに構成設定を格納できます。 (CMake プロジェクトでは [CMakeSettings.json](customize-cmake-settings.md) ファイルを使用します。)Visual Studio IDE では、IntelliSense とコード ナビゲーションに `CppProperties.json` が使用されます。 構成は名前/値のペアから成り、#include のパス、コンパイラ スイッチ、その他のパラメーターが定義されています。 


## <a name="default-configurations"></a>既定の構成

Visual Studio では、x86 と x64 のデバッグとリリースに対する定義済みの構成が提供されます。 既定では、x86 のデバッグ構成は `CppProperties.json` にあります。 新しい構成を追加するには、**ソリューション エクスプローラー**で `CppProperties.json` ファイルを右クリックして、**[構成の追加]** を選択します。

!["フォルダーを開く" の構成の追加](media/open-folder-add-config.png "\"フォルダーを開く\" の新しい構成の追加")

既定の構成を次に示します。

```json
{
  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86-Debug",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "_DEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86-Release",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "NDEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64-Debug",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "_DEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x64"
    },
    {
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64-Release",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "NDEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```
許容値のセットがあるプロパティの場合は、コード エディターで入力を始めると、使用可能なオプションが表示されます。

!["フォルダーを開く" の IntelliSense](media/open-folder-intellisense-mode.png "\"フォルダーを開く\" の IntelliSense")



## <a name="configuration-properties"></a>構成のプロパティ

構成には、次のどのプロパティでも含めることができます。

|||
|-|-|
|`name`|C++ の構成ドロップダウンに表示される構成の名前|
|`includePath`|インクルード パスで指定する必要があるフォルダーのリスト (ほとんどのコンパイラで /I に対応します)|
|`defines`|定義する必要のあるマクロのリスト (ほとんどのコンパイラで /D に対応します)|
|`compilerSwitches`|IntelliSense の動作に影響を与えることができる 1 つ以上の追加スイッチ|
|`forcedInclude`|すべてのコンパイル単位に自動的にインクルードされるヘッダー (MSVC の /FI または clang の -include に対応します)|
|`undefines`|未定義にするマクロのリスト (MSVC の /U に対応します)|
|`intelliSenseMode`|使用する IntelliSense エンジン。 MSVC、gcc、または Clang に対するアーキテクチャ固有のバリエーションを指定できます。<br/><br/>- windows-msvc-x86 (default)<br/>- windows-msvc-x64<br/>- msvc-arm<br/>- windows-clang-x86<br/>- windows-clang-x64<br/>- windows-clang-arm<br/>- Linux-x64<br/>- Linux-x86<br/>- Linux-arm<br/>- gccarm|

メモ:値`msvc-x86`と`msvc-x64`の旧システムのみがサポートされます。 使用してください、`windows-msvc*`バリアント。

## <a name="custom-configurations"></a>カスタム構成


`CppProperties.json` の既定の構成はどれでもカスタマイズすることができ、新しい構成を作成することもできます。 それぞれが、構成ドロップダウンに表示されます。

```json
{
  "configurations": [
    {
      "name": "Windows",
      ...
    },
    {
      "name": "with EXTERNAL_CODECS",
      ...
    }
  ]
}
```

## <a name="system-environment-variables"></a>システム環境変数 

 `CppProperties.json` では、インクルード パスと他のプロパティ値に対するシステム環境変数の展開がサポートされています。 環境変数 `%FOODIR%` を展開する場合の構文は `${env.FOODIR}` です。 次のシステム定義変数もサポートされます。

|変数名|説明|
|-----------|-----------------|
|vsdev|既定の Visual Studio 環境|
|msvc_x86|x86 ツールを使って、x86 用にコンパイルします|
|msvc_arm|x86 ツールを使って、ARM 用にコンパイルします|
|msvc_arm64|x86 ツールを使って、ARM64 用にコンパイルします|
|msvc_x86_x64|x86 ツールを使って、AMD64 用にコンパイルします|
|msvc_x64_x64|64 ビット ツールを使って、AMD64 用にコンパイルします|
|msvc_arm_x64|64 ビット ツールを使って、ARM 用にコンパイルします|
|msvc_arm64_x64|64 ビット ツールを使って、ARM64 用にコンパイルします|

Linux ワークロードがインストールされている場合、Linux および WSL をリモートでターゲットにするために次の環境変数を使用できます。

|変数名|説明|
|-----------|-----------------|
|linux_x86|x86 Linux をリモートでターゲットにします|
|linux_x64|x64 Linux をリモートでターゲットにします|
|linux_arm|ARM Linux をリモートでターゲットにします|

## <a name="custom-environment-variables"></a>カスタム環境変数

`CppProperties.json` では、カスタム環境変数をグローバルに、または構成単位で定義できます。 次の例では、既定の環境変数およびカスタム環境変数を宣言して使う方法を示します。 グローバルな **environments** プロパティでは、任意の構成で使用できる **INCLUDE** という名前の変数が宣言されています。

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\src\includes"
    }
  ],

  "configurations": [
    {
      "inheritEnvironments": [
        // Inherit the MSVC 32-bit environment and toolchain.
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "inheritEnvironments": [
        // Inherit the MSVC 64-bit environment and toolchain.
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```
## <a name="per-configuration-environment-variables"></a>構成ごとの環境変数

構成の内部で **environments** プロパティを定義することで、その構成のみにプロパティを適用して、同じ名前のグローバル変数をオーバーライドすることもできます。 次の例の x64 構成で定義されているローカルな **INCLUDE** 変数は、グローバルな値をオーバーライドします。

```json
{
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\src\includes"
    }
  ],

  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined in the global environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "environments": [
        {
          // Append 64-bit specific include path to env.INCLUDE.
          "INCLUDE": "${env.INCLUDE};${workspaceRoot}\src\includes64"
        }
      ],

      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined in the local environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```

すべてのカスタム環境変数と既定の環境変数は、`tasks.vs.json` および `launch.vs.json` でも使用できます。

#### <a name="build-in-macros"></a>組み込みマクロ

`CppProperties.json` 内の次の組み込みマクロにアクセスできます。

|||
|-|-|
|`${workspaceRoot}`| ワークスペース フォルダーへの完全なパスです|
|`${projectRoot}`| `CppProperties.json` が配置されているフォルダーへの完全なパスです|
|`${vsInstallDir}`| VS 2017 の実行中のインスタンスがインストールされているフォルダーへの完全なパスです|

たとえば、プロジェクトにインクルード フォルダーがあるだけでなく、windows.h および他の共通ヘッダーを Windows SDK からもインクルードしている場合、`CppProperties.json` の構成ファイルをこれらのインクルードで更新したい場合があります。

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\ucrt",
        "${env.NETFXSDKDir}\include\um",
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\um",
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\shared",
        "${env.VCToolsInstallDir}\include"
      ]
    }
  ]
}
```

> [!Note]
> `%WindowsSdkDir%` と `%VCToolsInstallDir%` はグローバル環境変数として設定されていないため、これらの変数を定義する devenv.exe は "開発者コマンド プロンプト for VS 2017" から起動してください。

## <a name="troubleshoot-intellisense-errors"></a>IntelliSense エラーのトラブルシューティング

インクルード パスがないことにより発生する IntelliSense のエラーをトラブルシューティングするには、**[エラー一覧]** を開き、出力を "IntelliSense のみ" およびエラー コード E1696 "ソース ファイル ... を開くことができません" でフィルター処理します。



