---
description: '詳細については、「_com_ptr_t:: QueryInterface」を参照してください。'
title: _com_ptr_t::QueryInterface
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
ms.openlocfilehash: 6c6ff19227c920aade762af295942d8058a17ad3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295342"
---
# <a name="_com_ptr_tqueryinterface"></a>_com_ptr_t::QueryInterface

**Microsoft 固有の仕様**

カプセル化されたインターフェイスポインターでの **QueryInterface** メンバー関数を呼び出し `IUnknown` ます。

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
`IID` インターフェイスポインターの。

*p*<br/>
生のインターフェイス ポインター。

## <a name="remarks"></a>解説

指定したを使用して、 `IUnknown::QueryInterface` カプセル化されたインターフェイスポインターでを呼び出し、結果として生成された `IID` 生のインターフェイスポインターを *p* に返します。 このルーチンは、成功または失敗を示す HRESULT を返します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
