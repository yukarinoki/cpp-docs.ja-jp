---
title: _com_ptr_t::Attach |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2fbedb2bbfba16abf1196d1dba377f7589c916b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099617"
---
# <a name="comptrtattach"></a>_com_ptr_t::Attach

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
場合は TRUE、`AddRef`が呼び出されます。 FALSE の場合、`_com_ptr_t`オブジェクト呼び出さずに生のインターフェイス ポインターの所有権を取得する`AddRef`します。

## <a name="remarks"></a>Remarks

- **アタッチ (***pInterface***)** `AddRef`は呼び出されません。 インターフェイスの所有権は、この `_com_ptr_t` オブジェクトに渡されます。 `Release` 以前にカプセル化されたポインターの参照カウントをデクリメントすると呼びます。

- **アタッチ (***pInterface* **、***fAddRef***)** 場合*fAddRef*が true の場合、 `AddRef`カプセル化されたインターフェイス ポインターの参照カウントをインクリメントすると呼びます。 場合*fAddRef* false で、この`_com_ptr_t`オブジェクト呼び出さずに生のインターフェイス ポインターの所有権を取得する`AddRef`します。 `Release` 以前にカプセル化されたポインターの参照カウントをデクリメントすると呼びます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)