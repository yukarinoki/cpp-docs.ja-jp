---
title: _com_ptr_t::QueryInterface |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0add1d8f3fc73f78cee3e10642d7b5a12968a6a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106873"
---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface

**Microsoft 固有の仕様**

呼び出し、 **QueryInterface**のメンバー関数`IUnknown`カプセル化されたインターフェイス ポインター。

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
`IID` インターフェイス ポインター。

*p*<br/>
生のインターフェイス ポインター。

## <a name="remarks"></a>Remarks

呼び出し`IUnknown::QueryInterface`指定してカプセル化されたインターフェイス ポインターで`IID`で、結果として得られる生のインターフェイス ポインターを返します*p*します。 このルーチンは、成功または失敗を示す HRESULT を返します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)