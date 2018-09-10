---
title: to_vector 関数 |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
dev_langs:
- C++
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3dcccc332a5d768a614414838003e1400f3c6a6
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107628"
---
# <a name="tovector-function"></a>to_vector 関数

値が、指定された IVector または IVectorView パラメーターの基になるコレクションと同じである `std::vector` を返します。

## <a name="syntax"></a>構文

```
template <typename T>
inline ::std::vector<T> to_vector(IVector<T>^ v);

template <typename T>
inline ::std::vector<T> to_vector(IVectorView<T>^ v);
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
テンプレート型パラメーター。

*v*<br/>
基になる Vector または VectorView オブジェクトへのアクセスを提供する IVector または IVectorView インターフェイス。

### <a name="return-value"></a>戻り値

### <a name="requirements"></a>要件

**ヘッダー:** collection.h

**名前空間:** Windows::Foundation::Collections

## <a name="see-also"></a>関連項目

[:Foundation Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)