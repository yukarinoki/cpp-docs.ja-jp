---
title: ダイアログ ボックスの破棄 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66a3ef9a72107ffb36a75834a6e197aba394c420
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343929"
---
# <a name="destroying-the-dialog-box"></a>ダイアログ ボックスの破棄
モーダル ダイアログ ボックスは通常、スタック フレーム上に作成し、それを作成した関数が終了すると破棄します。 ダイアログ オブジェクトのデストラクターは、オブジェクトがスコープ外に出るときに呼び出されます。  
  
 モードレス ダイアログ ボックスが通常作成され、親ビューまたはフレーム ウィンドウが所有する、アプリケーションのメイン フレーム ウィンドウまたはドキュメント フレーム ウィンドウです。 既定値[OnClose](../mfc/reference/cwnd-class.md#onclose)ハンドラーの呼び出し[DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)、ダイアログ ボックス ウィンドウを破棄します。 オーバーライドする場合は、ダイアログ ボックスがスタンドアロン、またはその他の特殊な所有権セマンティクスなしポインターの使用であり、 [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) C++ ダイアログ オブジェクトを破棄します。 オーバーライドする必要がありますも[OnCancel](../mfc/reference/cdialog-class.md#oncancel)を呼び出すと`DestroyWindow`から内にします。 それ以外の場合は、必要でなくなったときに ダイアログ ボックスのオーナーが C++ オブジェクトを破棄する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

