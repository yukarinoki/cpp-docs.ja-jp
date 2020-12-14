---
description: '詳細情報: begin 関数'
title: begin 関数
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::begin
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
ms.openlocfilehash: ae59a4b4344da520d86c216f4c9979953e16753c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302765"
---
# <a name="begin-function"></a>begin 関数

指定されたインターフェイス パラメーターによってアクセスされるコレクションの先頭を指す反復子を返します。

## <a name="syntax"></a>構文

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    begin(
          IVector<T>^ v         );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    begin(
          IVectorView<T>^ v
         );

template <typename T>
    ::Platform::Collections::InputIterator<T>
    begin(
          IIterable<T>^ i         );
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
テンプレート型パラメーター。

*v*<br/>
\<T> \<T> Ivector または IVectorView インターフェイスによってアクセスされる Vector オブジェクトまたは VectorView オブジェクトのコレクション \<T> \<T> 。

*i*<br/>
IIterable インターフェイスによってアクセスされる任意の Windows ランタイムオブジェクトのコレクション \<T> 。

### <a name="return-value"></a>戻り値

コレクションの先頭を指す反復子。

### <a name="remarks"></a>解説

最初の 2 つのテンプレート関数は反復子を返し、3 番目のテンプレート関数は入力反復子を返します。

Begin によって返される VectorIterator オブジェクトは、VectorProxy 型の要素を格納するプロキシ反復子です \<T> 。 ただし、プロキシ オブジェクトは、ユーザー コードにはほとんどは表示されません。 詳細については、「 [Collections (C++/CX) (コレクション (C++/CX))](../cppcx/collections-c-cx.md)」を参照してください。

### <a name="requirements"></a>要件

**ヘッダー:** collection.h

**名前空間:** Windows::Foundation::Collections

## <a name="see-also"></a>関連項目

[Windows:: Foundation:: Collections 名前空間](../cppcx/windows-foundation-collections-namespace-c-cx.md)
