---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 870e3580ed23ce994d832f7c59b951680d725e41
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180499"
---
# <a name="_com_ptr_tattach"></a>_com_ptr_t::Attach

**Microsoft 固有の仕様**

このスマート ポインターの型の生のインターフェイス ポインターをカプセル化します。

## <a name="syntax"></a>構文

```
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>パラメーター

*pInterface*<br/>
生のインターフェイス ポインター。

*fAddRef*<br/>
TRUE の場合、`AddRef` が呼び出されます。 FALSE の場合、`_com_ptr_t` オブジェクトは `AddRef`を呼び出さずに、生のインターフェイスポインターの所有権を取得します。

## <a name="remarks"></a>解説

- **Attach (**  *pinterface*  **)** `AddRef` は呼び出されません。 インターフェイスの所有権は、この `_com_ptr_t` オブジェクトに渡されます。 `Release` は、以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。

- **Attach (** *pinterface* **,** *faddref* **)** *Faddref*が TRUE の場合、カプセル化されたインターフェイスポインターの参照カウントをインクリメントするために `AddRef` が呼び出されます。 *Faddref*が FALSE の場合、この `_com_ptr_t` オブジェクトは `AddRef`を呼び出さずに、生のインターフェイスポインターの所有権を取得します。 `Release` は、以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
