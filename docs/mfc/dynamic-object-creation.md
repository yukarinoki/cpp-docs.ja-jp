---
title: オブジェクトの動的生成
ms.date: 03/27/2020
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
ms.openlocfilehash: 40a17d3ed458d0634fd5bf27b54d0a36a65e35b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364802"
---
# <a name="dynamic-object-creation"></a>オブジェクトの動的生成

この記事では、実行時にオブジェクトを動的に作成する方法について説明します。 この手順では、「ランタイム クラス情報へのアクセス」で説明されているように、[ランタイム クラス情報を](../mfc/accessing-run-time-class-information.md)使用します。

#### <a name="dynamically-create-an-object-given-its-run-time-class"></a>ランタイム クラスを指定してオブジェクトを動的に作成する

1. 次のコードを使用して、 の関数を使用`CreateObject`してオブジェクトを`CRuntimeClass`動的に作成します。 失敗した場合`CreateObject`は、例外を発生させる代わりに**NULL**を返します。

   [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>関連項目

[CObject を使用したウィンドウ オブジェクト](tn017-destroying-window-objects.md)
[の](using-cobject.md)破棄
