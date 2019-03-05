---
title: '方法: リボン コントロールとイベント ハンドラーを追加します。'
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
ms.openlocfilehash: 8a164101dc42241a2cc76c91a3baa66e02e4dc90
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291133"
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>方法: リボン コントロールとイベント ハンドラーを追加します。

リボン コントロールは、ボタンやコンボ ボックス、パネルに追加するなどの要素です。 パネルは、関連するコントロールのグループを表示するリボン バーの領域です。

このトピックでは、リボン デザイナーを開く、ボタンを追加、"Hello World"を表示するイベントをリンクします。

### <a name="to-open-the-ribbon-designer"></a>リボン デザイナーを開く

1. Visual Studio での**ビュー**  メニューのをクリックして**リソース ビュー**します。

1. **リソース ビュー**、デザイン画面上に表示するリボン リソースをダブルクリックします。

### <a name="to-add-a-button-and-an-event-handler"></a>ボタンと、イベント ハンドラーを追加するには

1. **ツールバー**、 をクリックして**ボタン**デザイン サーフェイス上のパネルにドラッグします。

1. ボタンを右クリックし、をクリックして**イベント ハンドラーの追加**します。

1. **イベント ハンドラー ウィザード**で既定の設定を確認し、をクリックして**の追加し、編集**します。 詳細については、次を参照してください。[イベント ハンドラー ウィザード](../ide/event-handler-wizard.md)します。

1. コード エディターでは、ハンドラー関数に次のコードを追加します。

```
    MessageBox((LPCTSTR)L"Hello World");
```

## <a name="see-also"></a>関連項目

[RibbonGadgets サンプル:リボンのガジェット アプリケーション](../visual-cpp-samples.md)<br/>
[リボン デザイナー (MFC)](../mfc/ribbon-designer-mfc.md)
