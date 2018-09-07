---
title: back_inserter 関数 |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::back_inserter
dev_langs:
- C++
helpviewer_keywords:
- back_inserter Function
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c013c769e4fc25ed1c8770bf5727a26da590680
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106426"
---
# <a name="backinserter-function"></a>back_inserter 関数

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

[:Foundation Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)