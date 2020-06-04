---
title: _com_ptr_t::QueryInterface
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
ms.openlocfilehash: 26dda2dff83ff0adbb7ef05c5e75f64b44138bd8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170672"
---
# <a name="_com_ptr_tqueryinterface"></a>_com_ptr_t::QueryInterface

**Microsoft 固有の仕様**

カプセル化されたインターフェイスポインターで `IUnknown` の**QueryInterface**メンバー関数を呼び出します。

## <a name="syntax"></a>構文

```
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType*& p
) throw ( );
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType** p
) throw( );
```

#### <a name="parameters"></a>パラメーター

*iid*<br/>
インターフェイスポインターの `IID`。

*p*<br/>
生のインターフェイス ポインター。

## <a name="remarks"></a>解説

指定した `IID` を使用して、カプセル化されたインターフェイスポインターで `IUnknown::QueryInterface` を呼び出し、結果の生のインターフェイスポインターを*p*に返します。 このルーチンは、成功または失敗を示す HRESULT を返します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
