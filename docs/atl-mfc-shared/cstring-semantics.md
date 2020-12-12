---
description: '詳細情報: CString セマンティクス'
title: CString の評価
ms.date: 11/04/2016
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
ms.openlocfilehash: 7c6dde91e7f87908c0c6bc2d49ff455eb79f6eb3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167046"
---
# <a name="cstring-semantics"></a>CString の評価

[CString](../atl-mfc-shared/reference/cstringt-class.md)オブジェクトは、拡張可能な動的オブジェクトであっても、組み込みのプリミティブ型および単純なクラスのように動作します。 各 `CString` オブジェクトは、一意の値を表します。 `CString` オブジェクトは、文字列へのポインターではなく、実際の文字列として考える必要があります。

1つ `CString` のオブジェクトを別のオブジェクトに割り当てることができます。 ただし、次の例に示すように、2つのオブジェクトのいずれかを変更しても、 `CString` もう一方の `CString` オブジェクトは変更されません。

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

この例では、2つの `CString` オブジェクトは同じ文字列を表すため、"equal" と見なされます。 クラスは、 `CString` 等値演算子 () をオーバーロードして、 `==` 2 つの `CString` オブジェクトの値 (コンテンツ) を id (アドレス) ではなく比較します。

## <a name="see-also"></a>関連項目

[文字列 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
