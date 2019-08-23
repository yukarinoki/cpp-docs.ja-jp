---
title: CppProperties.json スキーマ リファレンス
ms.date: 08/09/2019
helpviewer_keywords:
- CppProperties.json file [C++]
ms.openlocfilehash: 06029157b4b3826bc9c34a4434ab390f3eaa5a44
ms.sourcegitcommit: ace42fa67e704d56d03c03745b0b17d2a5afeba4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69975952"
---
# <a name="cpppropertiesjson-schema-reference"></a>CppProperties.json スキーマ リファレンス

CMake を使用しないオープンフォルダープロジェクトでは、IntelliSense のプロジェクト構成設定を*Cppproperties. json*ファイルに格納できます。 (CMake プロジェクトでは [CMakeSettings.json](customize-cmake-settings.md) ファイルを使用します。)構成は名前/値のペアから成り、#include のパス、コンパイラ スイッチ、その他のパラメーターが定義されています。 開いているフォルダープロジェクトに構成を追加する方法の詳細については、「[フォルダープロジェクトをC++開く](open-folder-projects-cpp.md)」を参照してください。

## <a name="configuration-properties"></a>構成のプロパティ

構成には、次のどのプロパティでも含めることができます。

|||
|-|-|
|`inheritEnvironments`| この構成に適用する環境を指定します。|
|`name`|C++構成ドロップダウンに表示される構成名|
|`includePath`|インクルードパスに指定する必要があるフォルダーのコンマ区切りのリスト (ほとんどのコンパイラでは/I にマップ)|
|`defines`|定義する必要のあるマクロのリスト (ほとんどのコンパイラで /D に対応します)|
|`compilerSwitches`|IntelliSense の動作に影響を与えることができる 1 つ以上の追加スイッチ|
|`forcedInclude`|すべてのコンパイル単位に自動的にインクルードされるヘッダー (MSVC の /FI または clang の -include に対応します)|
|`undefines`|未定義にするマクロのリスト (MSVC の /U に対応します)|
|`intelliSenseMode`|使用する IntelliSense エンジン。 MSVC、gcc、または Clang に対して定義済みのアーキテクチャ固有のバリアントの1つを指定できます。|
|`environments`|コマンドプロンプトで環境変数のように動作し、$ {env.} を使用してアクセスする、ユーザー<VARIABLE>定義の変数のセット。 マクロ.|

### <a name="intellisensemode-values"></a>intelliSenseMode の値

コードエディターでは、次のように入力を開始すると、使用可能なオプションが表示されます。

!["フォルダーを開く" の IntelliSense](media/open-folder-intellisense-mode.png "\"フォルダーを開く\" の IntelliSense")

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
- linux-gcc-arm

メモ:値 `msvc-x86` および `msvc-x64` は、レガシの理由でのみサポートされます。 代わりに、 `windows-msvc-*`バリアントを使用してください。

## <a name="pre-defined-environments"></a>定義済みの環境

Visual Studio には、対応する開発者コマンドプロンプトにC++マップされる、Microsoft 向けの次の定義済みの環境が用意されています。 これらの環境のいずれかを継承する場合は、次のマクロ構文で global プロパティ`env`を使用して、任意の環境変数を参照できます: $ {env。\<変数 >}。

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

## <a name="user_defined_environments"></a>ユーザー定義環境

必要に応じて、 `environments`プロパティを使用して、グローバルまたは構成ごとに*cppproperties. json*内の変数のセットを定義できます。 これらの変数は、開いているフォルダープロジェクトのコンテキストで環境変数のように動作し、$ {env\<を使用してアクセスできます。ここで定義された後に、 *json*からの変数 >} の構文と*起動... json。* ただし、Visual Studio が内部で使用するすべてのコマンドプロンプトで、実際の環境変数として設定されるとは限りません。

環境を使用する場合は、環境が同じ構成の一部と`inheritsEnvironments`して定義されている場合でも、プロパティに指定する`environment`必要があります。プロパティは環境の名前を指定します。 次の例は、MSYS2 インストールで GCC 用の IntelliSense を有効にするためのサンプル構成を示しています。 構成によって環境が`mingw_64`定義および継承される方法と、 `includePath`プロパティが変数に`INCLUDE`アクセスする方法に注意してください。

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

構成内で**環境**プロパティを定義すると、同じ名前のすべてのグローバル変数がオーバーライドされます。

## <a name="built-in-macros"></a>組み込みマクロ

*Cppproperties. json*内の次の組み込みマクロにアクセスできます。

|||
|-|-|
|`${workspaceRoot}`| ワークスペースフォルダーへの完全パスです。|
|`${projectRoot}`| *Cppproperties. json*が配置されているフォルダーへの完全パス|
|`${env.vsInstallDir}`| Visual Studio の実行中のインスタンスがインストールされているフォルダーへの完全パス|

### <a name="example"></a>例

プロジェクトにインクルードフォルダーがあり、Windows SDK の*windows .h*とその他の共通ヘッダーも含まれている場合は、次のインクルードを使用して*cppproperties. json*構成ファイルを更新することをお勧めします。

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

IntelliSense が表示されない場合は、**ツール** >  **オプション** > **テキストエディター** >  **CC++** 、詳細設定の順に移動して、トラブルシューティングを行うことができます。 > "**ログを有効**にする" を**true**に設定します。 最初に、**ログ記録レベル**を5に設定し、フィルターを8に**ログ記録**するようにします。

![診断ログ](media/diagnostic-logging.png)

出力は**出力ウィンドウ**にパイプ処理され、[出力元**の表示] を選択すると表示されます。ビジュアルC++ログ**。 出力には、IntelliSense が使用しようとしている実際のインクルードパスの一覧が含まれます。 パスが*Cppproperties. json*のパスと一致しない場合は、フォルダーを閉じて、キャッシュされた参照データを含む*vs*サブフォルダーを削除してみてください。

インクルード パスがないことにより発生する IntelliSense のエラーをトラブルシューティングするには、 **[エラー一覧]** を開き、出力を "IntelliSense のみ" およびエラー コード E1696 "ソース ファイル ... を開くことができません" でフィルター処理します。
