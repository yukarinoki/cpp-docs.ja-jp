---
description: '詳細情報: back_inserter 関数'
title: back_inserter 関数
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::back_inserter
helpviewer_keywords:
- back_inserter Function
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
ms.openlocfilehash: d2483c9947fbf3a7bc04024221ec6e582e416f84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223582"
---
# <a name="back_inserter-function"></a>back_inserter 関数

指定されたコレクションの末尾に要素を挿入するために使用される反復子を返します。

## <a name="syntax"></a>構文

```

template <typename T>
Platform::BackInsertIterator<T>
    back_inserter(IVector<T>^ v);

template<typename T>
Platform::BackInsertIterator<T>
   back_inserter(IObservableVector<T>^ v);
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
テンプレート型パラメーター。

*v*<br/>
基になるコレクションへのアクセスを提供するインターフェイス ポインター。

### <a name="return-value"></a>戻り値

反復子。

### <a name="requirements"></a>要件

**ヘッダー:** collection.h

**名前空間:** Windows::Foundation::Collections

## <a name="see-also"></a>関連項目

[Windows:: Foundation:: Collections 名前空間](../cppcx/windows-foundation-collections-namespace-c-cx.md)
