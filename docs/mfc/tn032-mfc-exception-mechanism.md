---
description: '詳細情報: テクニカルノート 32: MFC 例外機構'
title: 'テクニカル ノート 32: MFC 例外処理機構'
ms.date: 11/04/2016
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
ms.openlocfilehash: 847d78762aaf5e04c8a0c1eb2170e951d0b867bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215535"
---
# <a name="tn032-mfc-exception-mechanism"></a>テクニカル ノート 32: MFC 例外処理機構

以前のバージョンの Visual C++ では、標準 C++ 例外機構がサポートされていませんでした。 MFC が提供するマクロ **TRY/CATCH/THROW** は代わりに使用されました。 このバージョンの Visual C++ は、C++ 例外を完全にサポートしています。 このノートでは、スタックベースのオブジェクトを自動的にクリーンアップする方法など、前のマクロの高度な実装の詳細について説明します。 C++ 例外では既定でスタックアンワインドがサポートされるため、このテクニカルノートは不要になりました。

MFC マクロと新しい C++ キーワードの相違点の詳細については、「 [例外: Mfc マクロと C++ 例外の使用](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
