---
title: ドキュメントとビューをクリーンアップ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4325b0de10861fc76ee9ab816376f40ba0ba587
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437418"
---
# <a name="cleaning-up-documents-and-views"></a>ドキュメントとビューの後処理

フレームワークが呼び出す最初、ドキュメントが閉じている間、その[DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)メンバー関数。 ドキュメントの操作の実行中にヒープにメモリを割り当てた場合`DeleteContents`割り当てを解除することをお勧めします。

> [!NOTE]
>  ドキュメント データをドキュメントのデストラクターで割り当ては解除する必要があります。 SDI アプリケーションの場合は、ドキュメント オブジェクトを再利用する可能性があります。

ヒープに割り当てられたメモリを解放するビューのデストラクターをオーバーライドできます。

## <a name="see-also"></a>関連項目

[ドキュメントとビューの初期化と後処理](../mfc/initializing-and-cleaning-up-documents-and-views.md)

