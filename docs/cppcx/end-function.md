---
title: end Function |Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::end
dev_langs:
- C++
helpviewer_keywords:
- end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec25b92ca9ce21f72ff2fb573aae316ef1c19eac
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596651"
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
 `T`  
 テンプレート型パラメーター。  
  
 `v`  
 ベクターのコレクション\<T > または VectorView\<T >、IVector によってアクセスされるオブジェクト\<T >、または IVectorView\<T > インターフェイス。  
  
 `i`  
 Windows ランタイムの任意のコレクション オブジェクトを IIterable によりアクセスされる\<T > インターフェイス。  
  
### <a name="return-value"></a>戻り値  
 コレクションの末尾を越えて指す反復子。  
  
### <a name="remarks"></a>Remarks  
 最初の 2 つのテンプレート関数は反復子を返し、3 番目のテンプレート関数は入力反復子を返します。  
  
 [によって返される](../cppcx/platform-collections-vectorviewiterator-class.md) Platform::Collections::VectorViewIterator `end` オブジェクトは、 `VectorProxy<T>`型の要素を格納するプロキシ反復子です。 ただし、プロキシ オブジェクトは、ユーザー コードにはほとんどは表示されません。 詳細については、「 [Collections (C++/CX) (コレクション (C++/CX))](../cppcx/collections-c-cx.md)」を参照してください。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>関連項目  
 [:Foundation Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)