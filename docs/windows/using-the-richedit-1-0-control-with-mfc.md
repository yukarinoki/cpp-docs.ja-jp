---
title: MFC でリッチ エディット 1.0 コントロールの使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63bda924a91bb1f86494d844af037386d6e30292
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406348"
---
# <a name="using-the-richedit-10-control-with-mfc"></a>MFC でのリッチ エディット 1.0 コントロールの使用

リッチ エディット コントロールを使用するには、まず[AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2)リッチ エディット 2.0 コントロール (RICHED20 を読み込めません。DLL)、または呼び出す[AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit)古い RichEdit 1.0 コントロール (RICHED32 を読み込めません。DLL) です。

現在を使用することが[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)古い RichEdit 1.0 コントロールでは、クラスが`CRichEditCtrl`はリッチ エディット 2.0 コントロールをサポートするためにのみ設計されています。 RichEdit 1.0 とリッチ エディット 2.0 とよく似ていますが、ために、ほとんどのメソッドを使用します。ただしの 1.0 と 2.0 のコントロールをいくつかのメソッドが正常に動作しない可能性がありますまたはまったく動作しないようにいくつかの違いに注意してください。

## <a name="requirements"></a>要件

MFC

## <a name="see-also"></a>関連項目

[ダイアログ エディターのトラブルシューティング](../windows/troubleshooting-the-dialog-editor.md)<br/>
[ダイアログ エディター](../windows/dialog-editor.md)