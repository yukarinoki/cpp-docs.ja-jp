---
description: '詳細情報: OLE コモンダイアログクラス'
title: OLE コモン ダイアログ クラス
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- dialog classes [MFC], OLE
- OLE common dialog classes [MFC]
- common dialog classes [MFC]
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
ms.openlocfilehash: c30871c8f49be608f5ceeea3d84c86d483e20a81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222282"
---
# <a name="ole-common-dialog-classes"></a>OLE コモン ダイアログ クラス

これらのクラスは、多くの標準 OLE ダイアログボックスを実装することによって、一般的な OLE タスクを処理します。 また、OLE 機能の一貫したユーザーインターフェイスも用意されています。

[COleDialog](reference/coledialog-class.md)<br/>
すべての OLE ダイアログボックスの共通の実装を格納するために、フレームワークによって使用されます。 ユーザーインターフェイスカテゴリのすべてのダイアログボックスクラスは、この基本クラスから派生します。 `COleDialog` を直接使用することはできません。

[COleInsertDialog](reference/coleinsertdialog-class.md)<br/>
[オブジェクトの挿入] ダイアログボックスを表示します。これは、新しい OLE リンクまたは埋め込みアイテムを挿入するための標準ユーザーインターフェイスです。

[COlePasteSpecialDialog](reference/colepastespecialdialog-class.md)<br/>
[特殊な貼り付け] ダイアログボックスを表示します。このダイアログボックスは、[貼り付けの編集] を実装するための標準ユーザーインターフェイスです。

[COleLinksDialog](reference/colelinksdialog-class.md)<br/>
リンクされた項目に関する情報を変更するための標準ユーザーインターフェイスである [リンクの編集] ダイアログボックスを表示します。

[COleChangeIconDialog](reference/colechangeicondialog-class.md)<br/>
OLE 埋め込みまたはリンクされた項目に関連付けられているアイコンを変更するための標準ユーザーインターフェイスである [アイコンの変更] ダイアログボックスを表示します。

[COleConvertDialog](reference/coleconvertdialog-class.md)<br/>
OLE 項目をある種類から別の型に変換するための標準ユーザーインターフェイスである [変換] ダイアログボックスを表示します。

[COlePropertiesDialog](reference/colepropertiesdialog-class.md)<br/>
Windows のコモン OLE プロパティダイアログボックスをカプセル化します。 共通の OLE プロパティダイアログボックスを使用すると、Windows 標準と一貫性のある方法で OLE ドキュメントアイテムのプロパティを簡単に表示および変更することができます。

[COleUpdateDialog](reference/coleupdatedialog-class.md)<br/>
ドキュメント内のすべてのリンクを更新するための標準ユーザーインターフェイスである [更新] ダイアログボックスを表示します。 ダイアログボックスには、更新手順の終了方法を示す進行状況インジケーターが表示されます。

[COleChangeSourceDialog](reference/colechangesourcedialog-class.md)<br/>
リンク先を変更するための標準ユーザーインターフェイスである [変更ソース] ダイアログボックスを表示します。

[COleBusyDialog](reference/colebusydialog-class.md)<br/>
ビジー状態のアプリケーションの呼び出しを処理するための標準ユーザーインターフェイスである [サーバーがビジー] ダイアログボックスと [サーバーに応答しません] ダイアログボックスが表示されます。 通常、実装によって自動的に表示され `COleMessageFilter` ます。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
