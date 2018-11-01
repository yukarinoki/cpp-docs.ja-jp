---
title: MFC でのリッチ エディット 1.0 コントロールの使用
ms.date: 11/04/2016
helpviewer_keywords:
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
ms.openlocfilehash: 080ad995b9c7a041337d9b296d6ef8906e7f20ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468316"
---
# <a name="using-the-richedit-10-control-with-mfc"></a>MFC でのリッチ エディット 1.0 コントロールの使用

リッチ エディット コントロールを使用するには、まず[AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2)リッチ エディット 2.0 コントロール (RICHED20 を読み込めません。DLL)、または呼び出す[AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit)古い RichEdit 1.0 コントロール (RICHED32 を読み込めません。DLL) です。

現在を使用することが[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)古い RichEdit 1.0 コントロールでは、クラスが`CRichEditCtrl`はリッチ エディット 2.0 コントロールをサポートするためにのみ設計されています。 RichEdit 1.0 とリッチ エディット 2.0 とよく似ていますが、ために、ほとんどのメソッドを使用します。ただしの 1.0 と 2.0 のコントロールをいくつかのメソッドが正常に動作しない可能性がありますまたはまったく動作しないようにいくつかの違いに注意してください。

## <a name="requirements"></a>必要条件

MFC

## <a name="see-also"></a>関連項目

[ダイアログ エディターのトラブルシューティング](../windows/troubleshooting-the-dialog-editor.md)<br/>
[ダイアログ エディター](../windows/dialog-editor.md)