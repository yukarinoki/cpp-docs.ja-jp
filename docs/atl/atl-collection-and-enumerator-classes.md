---
description: '詳細情報: ATL コレクションと列挙子クラス'
title: ATL コレクションと列挙子クラス
ms.date: 11/04/2016
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
ms.openlocfilehash: b1f30aabb4908b0299a927f92a6d5ee4e9370a09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166045"
---
# <a name="atl-collection-and-enumerator-classes"></a>ATL コレクションと列挙子クラス

ATL には、コレクションと列挙子の実装に役立つ次のクラスが用意されています。

|クラス|説明|
|-----------|-----------------|
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|コレクションインターフェイスの実装|
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|列挙子インターフェイスの実装 (C++ 標準ライブラリと互換性のあるコンテナーに格納されているデータを想定)|
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|列挙子インターフェイスの実装 (配列に格納されているデータを想定)|
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|列挙子オブジェクトの実装 (を使用 `IEnumOnSTLImpl` )|
|[CComEnum](../atl/reference/ccomenum-class.md)|列挙子オブジェクトの実装 (を使用 `CComEnumImpl` )|
|[_Copy](../atl/atl-copy-policy-classes.md)|ポリシークラスのコピー|
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|ポリシークラスのコピー|
|[CAdapt](../atl/reference/cadapt-class.md)|Adapter クラス (、  、 `CComPtr` `CComQIPtr` および `CComBSTR` を C++ 標準ライブラリコンテナーに格納できるようにするために、演算子 &を非表示にします)|

## <a name="see-also"></a>関連項目

[コレクションと列挙子](../atl/atl-collections-and-enumerators.md)
