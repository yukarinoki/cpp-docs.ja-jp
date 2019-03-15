---
title: CppProperties.json スキーマ リファレンス
ms.date: 03/05/2019
helpviewer_keywords:
- CMake in Visual C++
ms.openlocfilehash: fd655de3313dd95eb3fcefaeba21e703d32e860a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826971"
---
# <a name="cpppropertiesjson-schema-reference"></a>CppProperties.json スキーマ リファレンス

CMake を使用していない開くフォルダーのプロジェクトがプロジェクトの構成設定を格納できる、`CppProperties.json`ファイル。 (CMake プロジェクトを使用して、 [CMakeSettings.json](customize-cmake-settings.md)ファイルです)。Visual Studio IDE を使用して`CppProperties.json`IntelliSense およびコード ナビゲーションの。 構成の名前/値ペアから成るし、定義 #include パス、コンパイラ スイッチ、およびその他のパラメーター。 


## <a name="default-configurations"></a>既定の構成

Visual Studio は、定義済みの構成を提供します。 x86 と x64 のデバッグ ビルドとリリースの。 既定では、プロジェクトはは、x86 デバッグの構成を持つ`CppProperties.json`します。 新しい構成を追加するを右クリックして、`CppProperties.json`ファイル**ソリューション エクスプ ローラー**選択**構成の追加**:

![構成を追加するフォルダーを開く](media/open-folder-add-config.png "新しい構成を追加するフォルダーを開く")

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
一連の許容値を持つプロパティ、については、コード エディターは、入力を開始するときに使用可能なオプションを示しています。

![IntelliSense のフォルダーを開く](media/open-folder-intellisense-mode.png "IntelliSense のフォルダーを開く")



## <a name="configuration-properties"></a>構成プロパティ

構成には、次のどのプロパティでも含めることができます。

|||
|-|-|
|`name`|C++ の [構成] ドロップダウン リストに表示される構成名|
|`includePath`|インクルード パス (/I にほとんどのコンパイラのマップ) で指定する必要があるフォルダーの一覧|
|`defines`|必要のあるマクロの一覧は、(ほとんどのコンパイラのマップを/D) を定義します。|
|`compilerSwitches`|IntelliSense の動作に影響を与える 1 つまたは複数のスイッチ|
|`forcedInclude`|すべてのコンパイル単位に自動的に含まれるヘッダー (/FI MSVC のマップまたは - clang を含める)|
|`undefines`|未定義 (MSVC の/U にマップ) を使用するマクロの一覧|
|`intelliSenseMode`|使用する IntelliSense エンジン。 MSVC、gcc、または Clang に対するアーキテクチャ固有のバリエーションを指定できます。<br/><br/>- msvc-x86 (既定)<br/>- msvc-x64<br/>- msvc-arm<br/>- windows-clang-x86<br/>- windows-clang-x64<br/>- windows-clang-arm<br/>- Linux-x64<br/>- Linux-x86<br/>- Linux-arm<br/>- gccarm|

## <a name="custom-configurations"></a>カスタム構成


既定 configuations のいずれかをカスタマイズする`CppProperties.json`、または新しい構成を作成します。 それぞれが、構成ドロップダウンに表示されます。

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

 `CppProperties.json` 用には、システム環境変数の拡張サポートするにはには、パスとその他のプロパティの値が含まれます。 環境変数 `%FOODIR%` を展開する場合の構文は `${env.FOODIR}` です。 次のシステム定義変数もサポートされます。

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

カスタム環境変数を定義する`CppProperties.json`か、グローバルに構成ごとまたは。 次の例では、既定の環境変数およびカスタム環境変数を宣言して使う方法を示します。 グローバルな **environments** プロパティでは、任意の構成で使用できる **INCLUDE** という名前の変数が宣言されています。

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
      "intelliSenseMode": "msvc-x86"
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
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```
## <a name="per-configuration-environment-variables"></a>環境変数を構成ごと

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
      "intelliSenseMode": "msvc-x86"
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
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```

すべてのカスタム既定の環境変数がでも利用できると`tasks.vs.json`と`launch.vs.json`します。

#### <a name="build-in-macros"></a>ビルド マクロ

内で次の組み込みマクロへのアクセスがある`CppProperties.json`:

|||
|-|-|
|`${workspaceRoot}`| ワークスペース フォルダーへの完全なパスです|
|`${projectRoot}`| フォルダーへの完全パスを`CppProperties.json`が配置されます|
|`${vsInstallDir}`| VS 2017 の実行中のインスタンスがインストールされているフォルダーへの完全なパスです|

たとえば、プロジェクトには、含めるフォルダーがあり、windows.h および Windows SDK から他の一般的なヘッダーも含まれます、場合を更新する、`CppProperties.json`これらの構成ファイルが含まれています。

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

## <a name="troubleshoot-intellisense-errors"></a>IntelliSense エラーをトラブルシューティングします。

インクルード パスがないことにより発生する IntelliSense のエラーをトラブルシューティングするには、**[エラー一覧]** を開き、出力を "IntelliSense のみ" およびエラー コード E1696 "ソース ファイル ... を開くことができません" でフィルター処理します。



