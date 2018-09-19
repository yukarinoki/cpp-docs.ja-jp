---
title: _bstr_t::GetAddress |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetAddress
dev_langs:
- C++
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b3aa001270a3dc608fabf73fce28ce51eb9295e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031302"
---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress

**Microsoft 固有の仕様**

既存の文字列を解放し、新しく割り当てられた文字列のアドレスを返します。

## <a name="syntax"></a>構文

```
BSTR* GetAddress( );
```

## <a name="return-value"></a>戻り値

`BSTR` でラップされた `_bstr_t` へのポインター。

## <a name="remarks"></a>Remarks

**GetAddress**すべて影響`_bstr_t`オブジェクトをその共有を`BSTR`します。 1 つ以上`_bstr_t`を共有できる、`BSTR`コピー コンス トラクターを使用して、**演算子 =**。

## <a name="example"></a>例

参照してください[_bstr_t::assign](../cpp/bstr-t-assign.md)の例を使用して、 **GetAddress**します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_bstr_t クラス](../cpp/bstr-t-class.md)