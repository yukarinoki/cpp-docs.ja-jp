---
title: ビルド イベントの指定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.IVCEventTool.Description
dev_langs:
- C++
helpviewer_keywords:
- Pre-Link event
- build events [C++], specifying
- custom build steps [C++], build events
- builds [C++], events
- events [C++], build
- builds [C++], customizing C++
- build events [C++]
- post-build events
ms.assetid: 788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5940f0d6efaec402a4a85ed659f42d7eab1bf91d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="specifying-build-events"></a>ビルド イベントの指定

ビルド イベントを使用すると、リンク プロセスの前に、ビルドの開始前に、またはビルドの完了後に実行するコマンドを指定します。

ビルド イベントは、ビルド プロセスにおいてビルドがこれらのポイントに正常に達した場合にのみ実行されます。 ビルドにエラーが発生した場合、*ビルド後*イベントは発生しませんリンクのフェーズの前にもエラーが発生する場合、 *pre-link*も*ビルド後*イベント。発生します。 さらに、ファイルをリンクする必要がない場合、 *pre-link*イベントは発生しません。 *Pre-link*イベントもないリンク ステップが含まれていないプロジェクトで利用可能です。

ファイルをビルドする必要はありません、ビルド イベントは発生しません。

ビルド イベントの概要については、次を参照してください。[カスタム ビルド ステップとビルド イベント](../ide/understanding-custom-build-steps-and-build-events.md)です。

### <a name="to-specify-a-build-event"></a>ビルド イベントを指定するには

1. **ソリューション エクスプローラー**で、ビルド イベントを指定するプロジェクトを選択します。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。

1. **ビルド イベント**フォルダー、ビルド イベントのプロパティ ページを選択します。

1. ビルド イベントに関連付けられたプロパティを指定します。

   - **コマンドライン**、コマンド プロンプトで指定するかのようにコマンドを指定します。 有効なコマンドまたはバッチ ファイルを指定し、いずれかの必須入力または出力ファイル。 指定して、**呼び出す**バッチ ファイルの名前の前にすべての後続のコマンドが実行されることを保証するために、コマンドをバッチ処理します。

      複数の入力と出力ファイルは、MSBuild マクロでのシンボルで指定できます。 ファイルの場所または一連のファイルの名前を指定する方法については、次を参照してください。[のビルドのコマンドとプロパティの一般的なマクロ](../ide/common-macros-for-build-commands-and-properties.md)です。

      '%' 文字は、各環境変数を置き換える、指定した場合、MSBuild によって予約されているため**%** 文字をエスケープ、 **%25** 16 進数のエスケープ シーケンスです。 たとえば、置き換える **%windir%** で **%25windir 25**です。 各 MSBuild が置き換えられます **%25**とシーケンス、 **%** 文字の環境変数にアクセスする前にします。

   - **説明**、このイベントの説明を入力します。 説明に出力され、**出力**このイベントが発生したときにウィンドウです。

   - **ビルドから除外**、指定**はい**イベントを実行したくない場合。

## <a name="see-also"></a>関連項目

[カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)  
[ビルドのコマンドとプロパティの共通マクロ](../ide/common-macros-for-build-commands-and-properties.md)  
[ビルドのカスタマイズのトラブルシューティング](../ide/troubleshooting-build-customizations.md)  
