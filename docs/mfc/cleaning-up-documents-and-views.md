---
title: ドキュメントとビューの後処理
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 8cb6e9337b69daf78286f57898c9badf513c7921
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626525"
---
# <a name="cleaning-up-documents-and-views"></a>ドキュメントとビューの後処理

ドキュメントを閉じると、フレームワークは最初に[DeleteContents](reference/cdocument-class.md#deletecontents)メンバー関数を呼び出します。 ドキュメントの操作中にヒープにメモリを割り当てた場合、は、その割り当て `DeleteContents` を解除するのに最適な場所です。

> [!NOTE]
> ドキュメントのデストラクター内のドキュメントデータの割り当てを解除することはできません。 SDI アプリケーションの場合、ドキュメントオブジェクトが再利用される可能性があります。

ビューのデストラクターをオーバーライドして、ヒープに割り当てたメモリの割り当てを解除することができます。

## <a name="see-also"></a>関連項目

[ドキュメントとビューの初期化と後処理](initializing-and-cleaning-up-documents-and-views.md)
