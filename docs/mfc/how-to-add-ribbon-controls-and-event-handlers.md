---
description: '詳細については、「方法: リボンコントロールとイベントハンドラーを追加する」を参照してください。'
title: '方法: リボン コントロールとイベント ハンドラーを追加する'
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
ms.openlocfilehash: bffac6b27f809961e3ca7a4323f519c765526198
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290298"
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>方法: リボン コントロールとイベント ハンドラーを追加する

リボンコントロールは、ボタンやコンボボックスなど、パネルに追加する要素です。 パネルは、関連するコントロールのグループを表示するリボンバーの領域です。

このトピックでは、リボンデザイナーを開き、ボタンを追加して、"Hello World" と表示されるイベントをリンクします。

### <a name="to-open-the-ribbon-designer"></a>リボンデザイナーを開くには

1. Visual Studio の [ **表示** ] メニューで、[ **リソースビュー**] をクリックします。

1. **リソースビュー** で、リボンリソースをダブルクリックしてデザイン画面に表示します。

### <a name="to-add-a-button-and-an-event-handler"></a>ボタンとイベントハンドラーを追加するには

1. **ツールバー** の [**ボタン**] をクリックし、デザイン画面のパネルにドラッグします。

1. ボタンを右クリックし、[ **イベントハンドラーの追加**] をクリックします。

1. **イベントハンドラーウィザード** で、既定の設定を確認し、[**追加と編集**] をクリックします。 詳細については、「 [イベントハンドラーウィザード](../ide/adding-an-event-handler-visual-cpp.md#event-handler-wizard)」を参照してください。

1. コードエディターで、次のコードをハンドラー関数に追加します。

```
    MessageBox((LPCTSTR)L"Hello World");
```

## <a name="see-also"></a>関連項目

[RibbonGadgets サンプル: リボンガジェットアプリケーション](../overview/visual-cpp-samples.md)<br/>
[リボンデザイナー (MFC)](ribbon-designer-mfc.md)
