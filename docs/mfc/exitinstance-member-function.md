---
title: ExitInstance メンバー関数は、|Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords: []
dev_langs:
- C++
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 954d2248061ec571d9d2ba8804c1f7c97275cbfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="exitinstance-member-function"></a>ExitInstance メンバー関数
[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance)クラスのメンバー関数[CWinApp](../mfc/reference/cwinapp-class.md)関数が呼び出されるアプリケーションのコピーによって終了した、通常、ユーザー、アプリケーションを終了します。  
  
 オーバーライド`ExitInstance`グラフィック デバイス インターフェイス (GDI) のリソースの解放や、プログラムの実行時に使用されるメモリを解放するなどの特別なクリーンアップ処理を必要があるかどうか。 ただし、ドキュメントやビューなど、標準的なアイテムのクリーンアップは、これらのオブジェクトに固有のクリーンアップを行うためのオーバーライド可能な他の関数と、フレームワークによって提供されます。  
  
## <a name="see-also"></a>関連項目  
 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
