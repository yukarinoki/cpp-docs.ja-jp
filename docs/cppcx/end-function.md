---
description: '詳細情報: end 関数'
title: end 関数
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::end
helpviewer_keywords:
- end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
ms.openlocfilehash: e29595e7eb403af85abdbfa18782adf1c33c308e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341972"
---
# <a name="end-function"></a>end 関数

指定されたインターフェイス パラメーターによってアクセスされるコレクションの末尾を越えて指す反復子を返します。

## <a name="syntax"></a>構文

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    end(
        IVector<T>^ v       );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    end(
        IVectorView<T>^ v
       );
template <typename T>
    ::Platform::Collections::InputIterator<T>
    end(
        IIterable<T>^ i
       );
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
テンプレート型パラメーター。

*v*<br/>
\<T> \<T> Ivector また \<T> は IVectorView インターフェイスによってアクセスされる vector オブジェクトまたは VectorView オブジェクトのコレクション \<T> 。

*i*<br/>
IIterable インターフェイスによってアクセスされる arbitraty Windows ランタイムオブジェクトのコレクション \<T> 。

### <a name="return-value"></a>戻り値

コレクションの末尾を越えて指す反復子。

### <a name="remarks"></a>解説

最初の 2 つのテンプレート関数は反復子を返し、3 番目のテンプレート関数は入力反復子を返します。

[によって返される](../cppcx/platform-collections-vectorviewiterator-class.md) Platform::Collections::VectorViewIterator `end` オブジェクトは、 `VectorProxy<T>`型の要素を格納するプロキシ反復子です。 ただし、プロキシ オブジェクトは、ユーザー コードにはほとんどは表示されません。 詳細については、「 [Collections (C++/CX) (コレクション (C++/CX))](../cppcx/collections-c-cx.md)」を参照してください。

### <a name="requirements"></a>要件

**ヘッダー:** collection.h

**名前空間:** Windows::Foundation::Collections

## <a name="see-also"></a>関連項目

[Windows:: Foundation:: Collections 名前空間](../cppcx/windows-foundation-collections-namespace-c-cx.md)
