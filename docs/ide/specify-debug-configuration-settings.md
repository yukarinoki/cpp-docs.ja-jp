---
title: 既存のコードから新しいプロジェクトを作成 - デバッグ設定 (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.debugsettings
dev_langs:
- C++
ms.assetid: 607339a8-9d33-458b-8095-dc73f374e29d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df50dfba79ad4160728e77b96d5814d6b03add1e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440891"
---
# <a name="specify-debug-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>[デバッグ構成の設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)

既存コード ファイルからの新しいプロジェクトの作成ウィザードのこのページを使用して、デバッグの構成プロジェクト設定を指定します。

## <a name="task-list"></a>タスク一覧

[方法 : 既存のコードから C++ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)

## <a name="uielement-list"></a>UIElement の一覧

- **ビルド コマンド ライン**

   新しいプロジェクトをビルドするコマンド ラインを指定します。 たとえば、コンパイラの名前 (とスイッチまたは引数) または新しいプロジェクトのビルドに使用するビルド スクリプトを入力します。 **[プロジェクト設定の指定]** ページで **[外部のビルド システムを使用する]** オプションがオンになっている場合、このオプションは有効です。オフの場合は利用できません。

- **リビルド コマンド ライン**

   新しいプロジェクトをリビルドするコマンド ラインを指定します。 **[プロジェクト設定の指定]** ページで **[外部のビルド システムを使用する]** オプションがオンになっている場合、このオプションは有効です。オフの場合は利用できません。

- **クリーン コマンド ライン**

   新しいプロジェクトのビルド ツールによって生成されたサポート ファイルを削除するコマンドラインを指定します。 **[プロジェクト設定の指定]** ページで **[外部のビルド システムを使用する]** オプションがオンになっている場合、このオプションは有効です。オフの場合は利用できません。

- **出力 (デバッグ用)**

   新しいプロジェクトのデバッグ構成用の出力ファイルのディレクトリ パスを指定します。 **[プロジェクト設定の指定]** ページで **[外部のビルド システムを使用する]** オプションがオンになっている場合、このオプションは有効です。オフの場合は利用できません。

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
