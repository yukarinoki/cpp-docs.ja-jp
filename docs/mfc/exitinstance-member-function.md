---
title: ExitInstance メンバー関数
ms.date: 11/04/2016
f1_keywords: []
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
ms.openlocfilehash: b1c5b3a20f25f909188023ab1650bc41316d7a9f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637737"
---
# <a name="exitinstance-member-function"></a>ExitInstance メンバー関数

[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance)クラスのメンバー関数[CWinApp](../mfc/reference/cwinapp-class.md)アプリケーションのコピーを終了すると、通常、ユーザーがアプリケーションの終了結果として毎回と呼びます。

オーバーライド`ExitInstance`グラフィックス デバイス インターフェイス (GDI) のリソースを解放することや、プログラムの実行中に使用されるメモリの割り当てを解除などの特別なクリーンアップ処理を必要があるかどうか。 ただし、ドキュメント、ビューなどの標準的なアイテムのクリーンアップは、これらのオブジェクトに固有のクリーンアップを行うためのオーバーライド可能な他の関数と、フレームワークによって提供されます。

## <a name="see-also"></a>関連項目

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
