---
description: 詳細については、「標準コマンド」を参照してください。
title: 標準コマンド
ms.date: 11/04/2016
helpviewer_keywords:
- File menu
- identifiers [MFC], command IDs
- command IDs, standard commands
- OLE commands
- commands [MFC], standard
- standard command IDs
- Window menu commands
- standard commands
- View menu commands
- Edit menu standard commands
- Help [MFC], menus
- programmer-defined IDs [MFC]
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
ms.openlocfilehash: 09c0afecf5b34565c3ab14e276c7c43a20189a0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216744"
---
# <a name="standard-commands"></a>標準コマンド

フレームワークでは、多くの標準コマンドメッセージが定義されています。 これらのコマンドの Id は、通常、次のような形式になります。

**ID_** *ソース* _ *項目*

ここで、 *Source* はメニュー名、 *item* はメニュー項目です。 たとえば、[ファイル] メニューの [新規作成] コマンドのコマンド ID は ID_FILE_NEW です。 標準コマンド Id は、ドキュメントで太字で示されています。 プログラマが定義した Id は、周囲のテキストとは異なるフォントで表示されます。

次に、サポートされている最も重要なコマンドの一覧を示します。

*[ファイル] メニューのコマンド*<br/>
[新規]、[開く]、[閉じる]、[保存]、[名前を付けて保存]、[ページ設定]、[印刷設定]、[印刷]、[印刷プレビュー]、[終了]、および [最近使用したファイル]。

*[編集] メニューのコマンド*<br/>
クリア、すべてクリア、コピー、切り取り、検索、貼り付け、繰り返し、置換、すべて選択、元に戻す、やり直し。

*[表示] メニューのコマンド*<br/>
ツールバーとステータスバー。

*[ウィンドウ] メニューのコマンド*<br/>
[新規]、[整列]、[重ね]、[水平方向]、[垂直方向]、[分割] の順に並べます。

*[ヘルプ] メニューのコマンド*<br/>
インデックス、ヘルプ、およびについて説明します。

*OLE コマンド ([編集] メニュー)*<br/>
新しいオブジェクトの挿入、リンクの編集、リンクの貼り付け、特殊な貼り付け、および *typename* オブジェクト (動詞コマンド) を行います。

フレームワークは、これらのコマンドに対してさまざまなレベルのサポートを提供します。 コマンドの中には、定義済みのコマンド Id としてのみサポートされているものと、完全な実装でサポートされるものがあります。 たとえば、フレームワークでは、[ファイル] メニューの [開く] コマンドを実装しています。これには、新しいドキュメントオブジェクトを作成し、[開く] ダイアログボックスを表示して、ファイルを開いて読み取ります。 これに対して、ID_EDIT_COPY などのコマンドはコピーするデータの性質によって異なるため、自分で編集メニューにコマンドを実装する必要があります。

サポートされているコマンドと実装レベルの詳細については、「 [テクニカルノート 22](../mfc/tn022-standard-commands-implementation.md)」を参照してください。 標準コマンドは AFXRES.H ファイルで定義されています。

## <a name="see-also"></a>関連項目

[ユーザーインターフェイスオブジェクトとコマンド Id](../mfc/user-interface-objects-and-command-ids.md)
