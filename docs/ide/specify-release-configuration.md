---
title: '[既存のコードから新しいプロジェクトを作成] リリース構成'
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.importwiz.releasesettings
ms.assetid: 3e2fc73c-bdbd-4790-b2bd-d31731f0cece
ms.openlocfilehash: 10dec5e36531c9c0bf549b37bbfa892a624d0bf0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511822"
---
# <a name="specify-release-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>[リリースの構成の設定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)

既存コード ファイルからの新しいプロジェクトの作成ウィザードのこのページを使用して、リリースの構成プロジェクト設定を指定します。

## <a name="task-list"></a>タスク一覧

[方法 : 既存のコードから C++ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)

## <a name="uielement-list"></a>UIElement の一覧

- **デバッグ構成と同じ**

   デバッグ構成プロジェクト設定と同じリリース構成プロジェクト設定がウィザードで生成されるように指定します。 既定では、このオプションはオンになっています。 このボックスをオフにした場合を除き、このページの他のオプションはすべて非アクティブになります。

- **ビルド コマンド ライン**

   新しいプロジェクトをビルドするコマンド ラインを指定します。 コンパイラの名前と、新しいプロジェクトのビルドに使用するスイッチまたは引数を入力します。 **[プロジェクト設定の指定]** ページで **[外部のビルド システムを使用する]** オプションがオンになっている場合、このオプションは有効です。

- **リビルド コマンド ライン**

   新しいプロジェクトをリビルドするコマンド ラインを指定します。 **[プロジェクト設定の指定]** ページで **[外部のビルド システムを使用する]** オプションがオンになっている場合、このオプションは有効です。

- **クリーン コマンド ライン**

   新しいプロジェクトのビルド ツールによって生成されたサポート ファイルを削除するコマンドラインを指定します。 **[プロジェクト設定の指定]** ページで **[外部のビルド システムを使用する]** オプションがオンになっている場合、このオプションは有効です。

- **出力 (デバッグ用)**

   新しいプロジェクトのデバッグ構成用出力ファイルのディレクトリ パスを指定します。 **[プロジェクト設定の指定]** ページで **[外部のビルド システムを使用する]** オプションがオンになっている場合、このオプションは有効です。

- **プリプロセッサの定義 (/D)**

   新しいプロジェクトのプリプロセッサ シンボルを定義します。 詳細については、「 [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md)」を参照してください。

- **インクルードの検索パス (/I)**

   新しいプロジェクトのプリプロセッサ ディレクティブに渡されるファイル参照を解決するために、コンパイラによって検索されるディレクトリのリストに追加するディレクトリ パスを指定します。 詳細については、「[/I (追加インクルード ディレクトリ)](../build/reference/i-additional-include-directories.md)」を参照してください。

- **強制インクルード ファイル (/FI)**

   新しいプロジェクトのビルド時に処理するヘッダー ファイルを指定します。 詳細については、「[/FI (強制インクルード ファイルの名前の指定)](../build/reference/fi-name-forced-include-file.md)」を参照してください。

- **.NET アセンブリ検索パス (/AI)**

   新しいプロジェクトのプリプロセッサ ディレクティブに渡される .NET アセンブリ参照を解決するために、コンパイラによって検索されるディレクトリ パスを指定します。 詳細については、「[/AI (メタデータ ディレクトリの指定)](../build/reference/ai-specify-metadata-directories.md)」を参照してください。

- **強制 using .NET アセンブリ (/FU)**

   新しいプロジェクトのビルド時に処理する .NET アセンブリを指定します。 詳細については、「[/FU (強制 #using ファイルの名前の指定)](../build/reference/fu-name-forced-hash-using-file.md)」を参照してください。

## <a name="see-also"></a>参照

[[プロジェクト設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)