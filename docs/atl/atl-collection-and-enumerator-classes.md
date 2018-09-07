---
title: ATL コレクションと列挙子クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0ff5fec4749e08826bab5572149c6cd24a204f9
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765074"
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

