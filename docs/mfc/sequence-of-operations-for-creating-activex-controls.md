---
description: '詳細情報: ActiveX コントロールを作成するための一連の操作'
title: ActiveX コントロールの作成手順
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
- sequence [MFC], for creating ActiveX controls
- OLE controls [MFC], MFC
- sequence [MFC]
ms.assetid: 7d868c53-a0af-4ef6-a89c-e1c03c583a53
ms.openlocfilehash: 15b81716f5feee4dfd4d0ebf47ee4d0d648c4536
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217629"
---
# <a name="sequence-of-operations-for-creating-activex-controls"></a>ActiveX コントロールの作成手順

次の表に、ActiveX コントロール (旧称 OLE コントロール) の作成におけるロールとフレームワークの役割を示します。

### <a name="creating-activex-controls"></a>ActiveX コントロールの作成

|タスク|そうですよね|フレームワークは|
|----------|------------|------------------------|
|ActiveX コントロールフレームワークを作成します。|MFC ActiveX コントロールウィザードを実行して、コントロールを作成します。 [オプション] ページで、必要なオプションを指定します。 オプションには、プロジェクト内のコントロールの種類と名前、ライセンス、サブクラス、および About Box メソッドが含まれます。|MFC ActiveX コントロールウィザードでは、アプリケーション、コントロール、およびプロパティページのソースファイルなどの基本的な機能を使用して、ActiveX コントロールのファイルを作成します。リソースファイル。プロジェクトファイル。他にも、すべての仕様に合わせて調整されています。|
|独自のコードの行を追加せずに、コントロールと ActiveX コントロールウィザードで提供される機能を確認します。|ActiveX コントロールをビルドし、Internet Explorer または [TSTCON サンプル](../overview/visual-cpp-samples.md)を使用してテストします。|実行中のコントロールのサイズを変更したり、移動したりすることができます。 また、呼び出せるよう **に、[About Box]** (選択されている場合) メソッドもあります。|
|コントロールのメソッドとプロパティを実装します。|コントロールのデータに公開されたインターフェイスを提供するメンバー関数を追加することによって、コントロール固有のメソッドとプロパティを実装します。 メンバー変数を追加してデータ構造を保持し、イベントハンドラーを使用してを決定したときにイベントを発生させます。|フレームワークでは、コントロールのイベント、プロパティ、およびメソッドをサポートするマップが既に定義されているため、プロパティとメソッドの実装方法に焦点を当てることができます。 既定のプロパティページが表示され、既定の About Box メソッドが提供されます。|
|コントロールのプロパティページを構築します。|Visual C++ リソースエディターを使用して、コントロールのプロパティページインターフェイスを視覚的に編集します。<br /><br />-追加のプロパティページを作成します。<br />-ビットマップ、アイコン、およびカーソルを作成して編集します。<br /><br /> また、ダイアログエディターでプロパティページをテストすることもできます。|MFC アプリケーションウィザードによって作成される既定のリソースファイルには、必要なリソースが多数用意されています。 Visual C++ を使用すると、既存のリソースを編集したり、新しいリソースを簡単かつ視覚的に追加したりできます。|
|コントロールのイベント、メソッド、およびプロパティをテストします。|コントロールをリビルドし、テストコンテナーを使用して、ハンドラーが正しく動作することをテストします。|プロパティページインターフェイスまたはテストコンテナーを使用して、コントロールのメソッドを呼び出し、そのプロパティを操作できます。 さらに、テストコンテナーを使用して、コントロールから発生したイベントと、コントロールのコンテナーによって受信された通知を追跡します。|

## <a name="see-also"></a>関連項目

[フレームワークでのビルド](../mfc/building-on-the-framework.md)<br/>
[MFC アプリケーションをビルドするための一連の操作](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[OLE アプリケーションを作成するための一連の操作](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[データベースアプリケーションを作成するための一連の操作](../mfc/sequence-of-operations-for-creating-database-applications.md)
