---
title: ExitInstance メンバー関数 |Microsoft Docs
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
ms.openlocfilehash: da411fbecdea0a1e7b8976ca119057204693a9bd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387862"
---
# <a name="exitinstance-member-function"></a>ExitInstance メンバー関数

[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance)クラスのメンバー関数[CWinApp](../mfc/reference/cwinapp-class.md)アプリケーションのコピーを終了すると、通常、ユーザーがアプリケーションの終了結果として毎回と呼びます。

オーバーライド`ExitInstance`グラフィックス デバイス インターフェイス (GDI) のリソースを解放することや、プログラムの実行中に使用されるメモリの割り当てを解除などの特別なクリーンアップ処理を必要があるかどうか。 ただし、ドキュメント、ビューなどの標準的なアイテムのクリーンアップは、これらのオブジェクトに固有のクリーンアップを行うためのオーバーライド可能な他の関数と、フレームワークによって提供されます。

## <a name="see-also"></a>関連項目

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
