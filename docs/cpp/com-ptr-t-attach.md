---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 057d784bb495aefaeec1b86697a7421f6464cbd7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745073"
---
# <a name="_com_ptr_tattach"></a>_com_ptr_t::Attach

**マイクロソフト固有**

このスマート ポインターの型の生のインターフェイス ポインターをカプセル化します。

## <a name="syntax"></a>構文

```cpp
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>パラメーター

*インターフェイス*<br/>
生のインターフェイス ポインター。

*ファドレフ*<br/>
TRUE の場合は呼`AddRef`び出されます。 FALSE の場合、`_com_ptr_t`オブジェクトは、呼び出さず`AddRef`に生のインターフェイス ポインターの所有権を取得します。

## <a name="remarks"></a>解説

- **アタッチ(***p インタフェース*)**は**`AddRef`呼び出されません。     インターフェイスの所有権は、この `_com_ptr_t` オブジェクトに渡されます。 `Release`は、以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。

- **アタッチ(***p インターフェイス* **、***fAddRef***)***fAddRef*が TRUE`AddRef`の場合は、カプセル化されたインターフェイス ポインターの参照カウントをインクリメントするために呼び出されます。       *fAddRef*が FALSE`_com_ptr_t`の場合、このオブジェクトは、呼び出`AddRef`しを行わずに生のインターフェイス ポインターの所有権を取得します。 `Release`は、以前にカプセル化されたポインターの参照カウントをデクリメントするために呼び出されます。

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
