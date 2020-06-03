---
title: ドキュメントとビューの後処理
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 06ff60a2cf6245f64e80d899c13a8444558fcf0b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374621"
---
# <a name="cleaning-up-documents-and-views"></a>ドキュメントとビューの後処理

ドキュメントが閉じるときに、フレームワークは最初に[DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)メンバー関数を呼び出します。 ドキュメントの操作中にヒープにメモリを割り当てた場合は、`DeleteContents`メモリの割り当てを解除する最適な場所です。

> [!NOTE]
> ドキュメントのデストラクターのドキュメント データの割り当てを解除しないでください。 SDI アプリケーションの場合、ドキュメント オブジェクトが再利用される場合があります。

ビューのデストラクタをオーバーライドして、ヒープに割り当てたメモリの割り当てを解除できます。

## <a name="see-also"></a>関連項目

[ドキュメントとビューの初期化と後処理](../mfc/initializing-and-cleaning-up-documents-and-views.md)
