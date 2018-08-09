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
- rich edit controls, RichEdit 1.0
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a00642c1aefdce57c37723ef4daf23381cee3c13
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650749"
---
# <a name="using-the-richedit-10-control-with-mfc"></a>MFC でのリッチ エディット 1.0 コントロールの使用
リッチ エディット コントロールを使用するには、まず[AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2)リッチ エディット 2.0 コントロール (RICHED20 を読み込めません。DLL)、または呼び出す[AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit)古い RichEdit 1.0 コントロール (RICHED32 を読み込めません。DLL) です。  
  
 現在を使用することが[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)古い RichEdit 1.0 コントロールでは、クラスが`CRichEditCtrl`はリッチ エディット 2.0 コントロールをサポートするためにのみ設計されています。 RichEdit 1.0 とリッチ エディット 2.0 とよく似ていますが、ために、ほとんどのメソッドを使用します。ただしの 1.0 と 2.0 のコントロールをいくつかのメソッドが正常に動作しない可能性がありますまたはまったく動作しないようにいくつかの違いに注意してください。  
  
## <a name="requirements"></a>要件  
 MFC  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ エディターのトラブルシューティング](../windows/troubleshooting-the-dialog-editor.md)   
 [ダイアログ エディター](../windows/dialog-editor.md)