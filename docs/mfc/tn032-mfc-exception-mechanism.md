---
title: 'TN032: MFC 例外処理機構 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.exceptions
dev_langs:
- C++
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aee8ce02af874e1c3c30243a35e8f36acfce63f0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414759"
---
# <a name="tn032-mfc-exception-mechanism"></a>テクニカル ノート 32: MFC 例外処理機構

Visual C の以前のバージョンが、標準の C++ 例外機構をサポートしていませんでしたし、MFC には、マクロが提供されている**TRY、CATCH、/THROW**代わりにで使用されました。 このバージョンの Visual C には、C++ の例外を完全にサポートしています。 この注は、前のマクロの高度な実装の詳細をいくつか紹介スタック ベースのオブジェクトを自動的にクリーンアップする方法についても触れます。 C++ の例外のスタック アンワインドを既定ではサポートされているためこの技術的な注意は必要はなくなりました。

参照してください[例外: を使用して MFC マクロと C++ 例外](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)MFC マクロと C++ のキーワードの違いの詳細についてはします。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

