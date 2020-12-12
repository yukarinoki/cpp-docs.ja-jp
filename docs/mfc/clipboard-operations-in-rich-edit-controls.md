---
description: '詳細情報: リッチエディットコントロールでのクリップボード操作'
title: リッチ エディット コントロールでのクリップボード操作
ms.date: 11/04/2016
helpviewer_keywords:
- pasting Clipboard data
- CRichEditCtrl class [MFC], paste operation
- cut operation in CRichEditCtrl class [MFC]
- CRichEditCtrl class [MFC], Clipboard operations
- copy operations in rich edit controls
- Clipboard, operations in CRichEditCtrl
- rich edit controls [MFC], Clipboard operations
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
ms.openlocfilehash: 9a9fda9aebe3a749359776c1bc0d41e75deaef76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251207"
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>リッチ エディット コントロールでのクリップボード操作

アプリケーションでは、クリップボードの内容をリッチエディットコントロール ([CRichEditCtrl](reference/cricheditctrl-class.md)) に貼り付けることができます。これは、最適なクリップボード形式または特定のクリップボード形式を使用します。 また、リッチエディットコントロールがクリップボード形式を貼り付けることができるかどうかを判断することもできます。

[Copy](reference/cricheditctrl-class.md#copy)または[cut](reference/cricheditctrl-class.md#cut)メンバー関数を使用して、現在の選択内容をコピーまたは切り取りできます。 同様に、 [paste](reference/cricheditctrl-class.md#paste) メンバー関数を使用すると、クリップボードの内容をリッチエディットコントロールに貼り付けることができます。 コントロールは、認識されている最初の使用可能な形式を貼り付けます。これは、おそらく最もわかりやすい形式です。

特定のクリップボード形式を貼り付けるには、 [PasteSpecial](reference/cricheditctrl-class.md#pastespecial) メンバー関数を使用します。 この関数は、ユーザーがクリップボード形式を選択できるようにするための、貼り付けの特別なコマンドを使用するアプリケーションに便利です。 [CanPaste](reference/cricheditctrl-class.md#canpaste)メンバー関数を使用すると、指定した書式がコントロールによって認識されているかどうかを判断できます。

また、を使用し `CanPaste` て、リッチエディットコントロールによって使用可能なクリップボード形式が認識されるかどうかを判断することもできます。 この関数は、ハンドラーで役に立ち `OnInitMenuPopup` ます。 アプリケーションでは、使用可能な任意の形式をコントロールが貼り付けることができるかどうかに応じて、貼り付けコマンドを有効または灰色にすることができます。

リッチエディットコントロールは、リッチテキスト形式と、RichEdit テキストおよびオブジェクトという形式の2つのクリップボード形式を登録します。 アプリケーションでは、 **CF_RTF** と **CF_RETEXTOBJ** の値を指定して、 [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw)関数を使用してこれらの形式を登録できます。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](using-cricheditctrl.md)<br/>
[コントロール](controls-mfc.md)
