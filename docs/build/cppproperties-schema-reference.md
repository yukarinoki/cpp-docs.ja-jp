---
title: 参照
ms.date: 08/09/2019
helpviewer_keywords:
- CppProperties.json file [C++]
ms.openlocfilehash: be6db52e1e62244e9f44db8ac86238242ab50ca0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328719"
---
# <a name="cpppropertiesjson-reference"></a>参照

CMake を使用しないフォルダー プロジェクトを開くと、IntelliSense のプロジェクト構成設定を*CppProperties.json*ファイルに格納できます。 (CMake プロジェクトは[CMakeSettings.json](customize-cmake-settings.md)ファイルを使用します。構成は、名前と値のペアで構成され、#includeパス、コンパイラ スイッチ、およびその他のパラメーターを定義します。 フォルダー[を開くプロジェクトで](open-folder-projects-cpp.md)構成を追加する方法の詳細については、「C++ 用のフォルダー プロジェクトを開く」を参照してください。 以下のセクションでは、さまざまな設定について説明します。 スキーマの詳細については *、cppProperties.json*が開いているときにコード エディターの先頭に完全なパスが指定されている*CppProperties_schema.json*に移動します。

## <a name="configuration-properties"></a>構成プロパティ

構成には、次のどのプロパティでも含めることができます。

|||
|-|-|
|`inheritEnvironments`| この構成に適用する環境を指定します。|
|`name`|C++ 構成ドロップダウンに表示される構成名|
|`includePath`|インクルード パスで指定する必要があるフォルダーのコンマ区切りリスト (ほとんどのコンパイラでは /I に対応)|
|`defines`|定義する必要のあるマクロのリスト (ほとんどのコンパイラで /D に対応します)|
|`compilerSwitches`|IntelliSense の動作に影響を与えることができる 1 つ以上の追加スイッチ|
|`forcedInclude`|すべてのコンパイル単位に自動的にインクルードされるヘッダー (MSVC の /FI または clang の -include に対応します)|
|`undefines`|未定義にするマクロのリスト (MSVC の /U に対応します)|
|`intelliSenseMode`|使用する IntelliSense エンジン。 MSVC、gcc、または Clang に対して、事前定義されたアーキテクチャ固有のバリアントのいずれかを指定できます。|
|`environments`|コマンド プロンプトで環境変数のように動作し、${env でアクセスされるユーザー定義の変数のセット。\<変数>} マクロ。|

### <a name="intellisensemode-values"></a>値

コード エディターには、入力を開始するときに使用可能なオプションが表示されます。

![フォルダのインテリセンスを開く](media/open-folder-intellisense-mode.png "フォルダのインテリセンスを開く")

サポートされている値は次のとおりです。

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
- linux-gccアーム

注: 値`msvc-x86`は`msvc-x64`、従来の理由でのみサポートされます。 代わりに`windows-msvc-*`バリアントを使用してください。

## <a name="pre-defined-environments"></a>事前定義された環境

Visual Studio には、対応する開発者コマンド プロンプトにマップする Microsoft C++ 用の次の定義済み環境が用意されています。 これらの環境のいずれかを継承する場合は、次のマクロ構文を持つグローバル プロパティ`env`を使用して、環境変数を参照できます。\<変数>}

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

## <a name="user-defined-environments"></a><a name="user_defined_environments"></a>ユーザー定義環境

オプションで、このプロパティを`environments`使用して、グローバルまたは構成ごとに *、CppProperties.json*で変数のセットを定義できます。 これらの変数は、フォルダーを開くプロジェクトのコンテキストで環境変数のように動作し、${env でアクセスできます。\<変数>} 構文は、ここで定義された後の*tasks.vs.json*および*launch.vs.json*から取得します。 ただし、Visual Studio が内部的に使用するコマンド プロンプトでは、実際の環境変数として設定されている必要はありません。

**Visual Studio 2019 バージョン 16.4 以降:***CppProperties.json*で定義された構成固有の変数は、設定する必要なしにデバッグターゲットとタスクによって自動的`inheritEnvironments`に取り込まれます。 デバッグ ターゲットは *、CppProperties.json*で指定した環境で自動的に起動されます。

**Visual Studio 2019 バージョン 16.3 以前:** 環境を使用する場合、環境が同じ構成の`inheritsEnvironments`一部として定義されている場合でも、プロパティで指定する必要があります。プロパティ`environment`は、環境の名前を指定します。 次の例は、MSYS2 インストールで GCC の IntelliSense を有効にするための構成例を示しています。 設定が`mingw_64`環境をどのように定義し、継承し、プロパティが変数に`includePath`アクセスできるかを`INCLUDE`確認します。

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

設定内で**環境**プロパティを定義すると、同じ名前のグローバル変数がオーバーライドされます。

## <a name="built-in-macros"></a>組み込みマクロ

*CppProperties.json*内の次の組み込みマクロにアクセスできます。

|||
|-|-|
|`${workspaceRoot}`| ワークスペース フォルダーへの完全パス|
|`${projectRoot}`| *CppProperties.json*が配置されているフォルダーへの完全パス|
|`${env.vsInstallDir}`| 実行中の Visual Studio のインスタンスがインストールされているフォルダーへの完全パス|

### <a name="example"></a>例

プロジェクトにインクルード フォルダーがあり、Windows SDK の*windows.h*やその他の一般的なヘッダーも含まれている場合は *、CppProperties.json*構成ファイルを次の内容で更新できます。

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

期待する IntelliSense が表示されない場合は、[**ツール** > **オプション** > **テキスト エディター** > **C/C++** > **詳細設定**] に進み、[**ログ記録を有効**にする] を**true**に設定してトラブルシューティングを行うことができます。 まず、[**ログ出力レベル]** を 5 に設定し、[**ログ フィルタ] を**8 に設定します。

![診断ログ](media/diagnostic-logging.png)

出力は**出力ウィンドウ**にパイプされ、[出力を表示] メニュー**の [Visual C++ ログ]** をクリックすると表示されます。 出力には、IntelliSense が使用しようとしている実際のインクルード パスの一覧が含まれています。 パスが*CppProperties.json*のパスと一致しない場合は、フォルダーを閉じて、キャッシュされた参照データを含む *.vs*サブフォルダーを削除してみてください。

インクルード パスがないことにより発生する IntelliSense のエラーをトラブルシューティングするには、**[エラー一覧]** を開き、出力を "IntelliSense のみ" およびエラー コード E1696 "ソース ファイル ... を開くことができません" でフィルター処理します。
