---
title: CString セマンティクス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 256c71cace15a3906ac048819ab2ffdef2071ff4
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761274"
---
# <a name="cstring-semantics"></a>CString の評価

でも[CString](../atl-mfc-shared/reference/cstringt-class.md)オブジェクトは、動的オブジェクトの拡張を許可する、組み込みのプリミティブ型と単純なクラスのように動作します。 各`CString`オブジェクトは、一意の値を表します。 `CString` オブジェクトは、文字列へのポインターではなく実際の文字列として考える必要があります。

1 つ割り当てることができます`CString`を別のオブジェクト。 ただし、変更する場合、2 つのいずれかの`CString`、もう一方のオブジェクト`CString`次の例に示すように、オブジェクトを変更しません。

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

例では、の注意事項を 2 つ`CString`オブジェクトと見なされる"equal"同じ文字の文字列を表すため。 `CString`クラスは、等値演算子をオーバー ロード (`==`) 2 つを比較する`CString`オブジェクト id (アドレス) ではなく、値 (内容) をベースにします。

## <a name="see-also"></a>関連項目

[文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)

