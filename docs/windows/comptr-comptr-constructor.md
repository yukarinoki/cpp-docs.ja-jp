---
title: Comptr::comptr コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ComPtr
dev_langs:
- C++
helpviewer_keywords:
- ComPtr, constructor
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ae03de851d7cf24d7322ff6f9e1f8610a584b376
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606217"
---
# <a name="comptrcomptr-constructor"></a>ComPtr::ComPtr コンストラクター

新しいインスタンスを初期化します、 **ComPtr**クラス。 オーバーロードは、既定、コピー、移動、および変換の各コンストラクターを提供します。

## <a name="syntax"></a>構文

```cpp
WRL_NOTHROW ComPtr();
WRL_NOTHROW ComPtr(
   decltype(__nullptr)  
);
template<class U>
WRL_NOTHROW ComPtr(
   _In_opt_ U *other
);
WRL_NOTHROW ComPtr(
   const ComPtr& other
);
template<class U>
WRL_NOTHROW ComPtr(
   const ComPtr<U> &other,
   typename ENABLE_IF<__is_convertible_to(U*,
   T*),
   void *>;
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr<U>&& other,
   typename ENABLE_IF<__is_convertible_to(U*,
   T*),
   void *>;
```

### <a name="parameters"></a>パラメーター

*U*  
種類、*他*パラメーター。

*other*  
型のオブジェクト*U*します。

## <a name="return-value"></a>戻り値

## <a name="remarks"></a>Remarks

最初のコンス トラクターは、どの暗黙的は、空のオブジェクトを作成します。 既定のコンス トラクターです。 2 番目のコンス トラクターを指定します[_ _nullptr](../windows/nullptr-cpp-component-extensions.md)を明示的に空のオブジェクトを作成します。

3 番目のコンス トラクターは、ポインターで指定されたオブジェクトからオブジェクトを作成します。

4 番目と 5 番目のコンス トラクターは、コピー コンス トラクターです。 5 番目のコンス トラクターは、現在の型に変換可能である場合、オブジェクトをコピーします。

6 番目と 7 番目のコンス トラクターは、移動コンス トラクターです。 7 番目のコンス トラクターは、現在の型に変換可能である場合、オブジェクトを移動します。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[ComPtr クラス](../windows/comptr-class.md)