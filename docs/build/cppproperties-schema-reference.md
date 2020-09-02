---
title: CppProperties.json リファレンス
ms.date: 08/09/2019
helpviewer_keywords:
- CppProperties.json file [C++]
ms.openlocfilehash: 31b4e7901bf35986e553a9e280da0243d61982a2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837906"
---
# <a name="cpppropertiesjson-reference"></a>CppProperties.json リファレンス

CMake を使用していない "フォルダーを開く" プロジェクトでは、*CppProperties.json* ファイルに IntelliSense のプロジェクト構成設定を格納できます。 (CMake プロジェクトでは [CMakeSettings.json](customize-cmake-settings.md) ファイルを使用します。)構成は名前/値のペアから成り、#include のパス、コンパイラ スイッチ、その他のパラメーターが定義されています。 "フォルダーを開く" プロジェクトに構成を追加する方法の詳細については、[C++ の "フォルダーを開く" プロジェクト](open-folder-projects-cpp.md)に関するページを参照してください。 次のセクションは、さまざまな設定をまとめたものです。 スキーマの詳細な説明については、*CppProperties_schema.json* に移動してください。この完全なパスは、*CppProperties.json* が開いているときにコード エディターの上部に示されます。

## <a name="configuration-properties"></a>構成プロパティ

構成には、次のどのプロパティでも含めることができます。

|Name|説明|
|-|-|
|`inheritEnvironments`| この構成に適用する環境を指定します。|
|`name`|C++ の構成ドロップダウンに表示される構成の名前|
|`includePath`|インクルード パスで指定する必要があるフォルダーのコンマ区切りのリスト (ほとんどのコンパイラで /I に対応します)|
|`defines`|定義する必要のあるマクロのリスト (ほとんどのコンパイラで /D に対応します)|
|`compilerSwitches`|IntelliSense の動作に影響を与えることができる 1 つ以上の追加スイッチ|
|`forcedInclude`|すべてのコンパイル単位に自動的にインクルードされるヘッダー (MSVC の /FI または clang の -include に対応します)|
|`undefines`|未定義にするマクロのリスト (MSVC の /U に対応します)|
|`intelliSenseMode`|使用する IntelliSense エンジン。 MSVC、gcc、または Clang に対する定義済みのアーキテクチャ固有バリアントの 1 つを指定できます。|
|`environments`|ユーザー定義の変数のセット。コマンド プロンプトで環境変数のように動作し、${env.\<VARIABLE>} マクロを使用してアクセスします。|

### <a name="intellisensemode-values"></a>intelliSenseMode 値

コード エディターでは、入力を開始すると、使用可能なオプションが次のように表示されます。

!["フォルダーを開く" の IntelliSense](media/open-folder-intellisense-mode.png "フォルダーを開く の IntelliSense")

サポートされる値は次のとおりです。

- windows-msvc-x86
- windows-msvc-x64
- windows-msvc-arm
- windows-msvc-arm64
- android-clang-x86
- android-clang-x64
- android-clang-arm
- android-clang-arm64
- ios-clang-x86
- ios-clang-x64
- ios-clang-arm
- ios-clang-arm64
- windows-clang-x86
- windows-clang-x64
- windows-clang-arm
- windows-clang-arm64
- linux-gcc-x86
- linux-gcc-x64
- linux-gcc-arm

メモ:値 `msvc-x86` および `msvc-x64` は、レガシの理由でのみサポートされます。 代わりに、`windows-msvc-*` のバリアントを使ってください。

## <a name="pre-defined-environments"></a>定義済みの環境

Visual Studio には、対応する開発者コマンド プロンプトにマップされる、Microsoft C++ 向けの次の定義済みの環境が用意されています。 これらの環境のいずれかを継承する場合は、グローバル プロパティ `env` をマクロ構文 ${env.\<VARIABLE>} で使用して、任意の環境変数を参照できます。

|変数名|説明|
|-----------|-----------------|
|vsdev|既定の Visual Studio 環境|
|msvc_x86|x86 ツールを使って、x86 用にコンパイルします|
|msvc_x64|64 ビット ツールを使って、AMD64 用にコンパイルします|
|msvc_arm|x86 ツールを使って、ARM 用にコンパイルします|
|msvc_arm64|x86 ツールを使って、ARM64 用にコンパイルします|
|msvc_x86_x64|x86 ツールを使って、AMD64 用にコンパイルします|
|msvc_arm_x64|64 ビット ツールを使って、ARM 用にコンパイルします|
|msvc_arm64_x64|64 ビット ツールを使って、ARM64 用にコンパイルします|

Linux ワークロードがインストールされている場合、Linux および WSL をリモートでターゲットにするために次の環境変数を使用できます。

|変数名|説明|
|-----------|-----------------|
|linux_x86|x86 Linux をリモートでターゲットにします|
|linux_x64|x64 Linux をリモートでターゲットにします|
|linux_arm|ARM Linux をリモートでターゲットにします|

## <a name="user-defined-environments"></a><a name="user_defined_environments"></a> ユーザー定義環境

必要に応じて `environments` プロパティを使用して、変数のセットを *CppProperties.json* にグローバルに、または構成単位で定義できます。 これらの変数は、"フォルダーを開く" プロジェクトのコンテキストで環境変数と同じように動作し、${env.\<VARIABLE>} 構文を使用して、ここで定義された後に *tasks.vs.json* および *launch.vs.json* からアクセスできます。 ただし、これらは、 Visual Studio が内部で使用するコマンド プロンプトで実際の環境変数として設定されるとは限りません。

**Visual Studio 2019 バージョン 16.4 以降:** *CppProperties.json* で定義されている構成固有の変数は、`inheritEnvironments` を設定しなくても、デバッグ ターゲットとタスクによって自動的に選択されます。 デバッグ ターゲットは、*CppProperties.json* で指定した環境で自動的に起動されます。

**Visual Studio 2019 バージョン 16.3 以前:** 環境を使用する場合は、その環境が同じ構成の一部として定義されている場合でも、それを `inheritsEnvironments` プロパティで指定する必要があります。`environment` プロパティは環境の名前を指定します。 次の例は、MSYS2 インストールで GCC 用の IntelliSense を有効にするためのサンプル構成を示しています。 構成によって `mingw_64` 環境が定義および継承される方法と、`includePath` プロパティが `INCLUDE` 変数にアクセスする方法に注意してください。

```json
"configurations": [
    {

      "inheritEnvironments": [
        "mingw_64"
      ],
      "name": "Mingw64",
      "includePath ,": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**",
      ],
      "intelliSenseMode": "linux-gcc-x64",
      "environments": [
        {
          "MINGW64_ROOT": "C:\\msys64\\mingw64",
          "BIN_ROOT": "${env.MINGW64_ROOT}\\bin",
          "FLAVOR": "x86_64-w64-mingw32",
          "TOOLSET_VERSION": "9.1.0",
          "PATH": "${env.MINGW64_ROOT}\\bin;${env.MINGW64_ROOT}\\..\\usr\\local\\bin;${env.MINGW64_ROOT}\\..\\usr\\bin;${env.MINGW64_ROOT}\\..\\bin;${env.PATH}",
          "INCLUDE": "${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION};${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\tr1;${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\${env.FLAVOR};",
          "environment": "mingw_64"
        }
      ]
    }
  ]
```

構成内で **environments** プロパティを定義すると、同じ名前のすべてのグローバル変数がオーバーライドされます。

## <a name="built-in-macros"></a>組み込みマクロ

*CppProperties.json* 内の次の組み込みマクロにアクセスできます。

|マクロ|説明|
|-|-|
|`${workspaceRoot}`| ワークスペース フォルダーへの完全なパスです|
|`${projectRoot}`| *CppProperties.json* が配置されているフォルダーへの完全なパスです|
|`${env.vsInstallDir}`| Visual Studio の実行中のインスタンスがインストールされているフォルダーへの完全なパスです|

### <a name="example"></a>例

プロジェクトにインクルード フォルダーがあるだけでなく、*windows.h* および他の共通ヘッダーも Windows SDK からインクルードしている場合、*CppProperties.json* の構成ファイルをこれらのインクルードで更新したい場合があります。

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
> `%WindowsSdkDir%` と `%VCToolsInstallDir%` はグローバル環境変数として設定されていないため、これらの変数を定義する devenv.exe を開発者コマンド プロンプトから実行する必要があります。 (Windows のスタート メニューで「開発者」と入力します。)

## <a name="troubleshoot-intellisense-errors"></a>IntelliSense エラーのトラブルシューティング

予期した IntelliSense が表示されない場合、トラブルシューティングを行うには、 **[ツール]**  >  **[オプション]**  >  **[テキスト エディター]**  >  **[C/C++]**  >  **[詳細設定]** に移動し、 **[ログを有効にする]** を **`true`** に設定にします。 最初は、 **[ログ記録レベル]** を [5] に設定し、 **[ログ フィルター]** を [8] に設定します。

![診断ログ記録](media/diagnostic-logging.png)

出力は**出力ウィンドウ**にパイプ処理され、 **[出力元の表示:Visual C++ ログ]** を選択したときに表示されます。 出力には、特に、IntelliSense が使用しようとしている実際のインクルード パスの一覧が含まれます。 そのパスが *CppProperties.json* のものと一致しない場合は、フォルダーを閉じて、キャッシュされた参照データが含まれている *.vs* サブフォルダーを削除してみてください。

インクルード パスがないことにより発生する IntelliSense のエラーをトラブルシューティングするには、 **[エラー一覧]** を開き、出力を "IntelliSense のみ" およびエラー コード E1696 "ソース ファイル ... を開くことができません" でフィルター処理します。
