---
title: ATL コレクションと列挙子クラス
ms.date: 11/04/2016
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
ms.openlocfilehash: a0d7483cc142377ec4de903e27f23056a9e8dd8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495305"
---
# <a name="atl-collection-and-enumerator-classes"></a>ATL コレクションと列挙子クラス

ATL には、コレクションと列挙子を実装するための次のクラスが用意されています。

|クラス|説明|
|-----------|-----------------|
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|コレクション インターフェイスの実装|
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|列挙子インターフェイスの実装 (C++ 標準ライブラリと互換性のあるコンテナーに格納されたデータを想定)|
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|列挙子インターフェイスの実装 (配列に格納されたデータを想定)|
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|列挙子オブジェクトの実装 (を使用して`IEnumOnSTLImpl`)|
|[CComEnum](../atl/reference/ccomenum-class.md)|列挙子オブジェクトの実装 (を使用して`CComEnumImpl`)|
|[コピー (_c)](../atl/atl-copy-policy-classes.md)|コピー ポリシー クラス|
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|コピー ポリシー クラス|
|[CAdapt](../atl/reference/cadapt-class.md)|アダプター クラス (非表示に**演算子 (& a)** 許可`CComPtr`、 `CComQIPtr`、および`CComBSTR`C++ 標準ライブラリ コンテナーに格納される)|

## <a name="see-also"></a>関連項目

[コレクションと列挙子](../atl/atl-collections-and-enumerators.md)

