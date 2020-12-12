---
description: '詳細については、「_bstr_t:: GetAddress」を参照してください。'
title: _bstr_t::GetAddress
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
ms.openlocfilehash: afb877a6f1b4cfcfb6fe08b36168af745d733b85
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229315"
---
# <a name="_bstr_tgetaddress"></a>_bstr_t::GetAddress

**Microsoft 固有の仕様**

既存の文字列を解放し、新しく割り当てられた文字列のアドレスを返します。

## <a name="syntax"></a>構文

```
BSTR* GetAddress( );
```

## <a name="return-value"></a>戻り値

`BSTR` でラップされた `_bstr_t` へのポインター。

## <a name="remarks"></a>解説

**Getaddress** `_bstr_t` は、を共有するすべてのオブジェクトに影響 `BSTR` します。 複数 `_bstr_t` ので、 `BSTR` コピーコンストラクターと **演算子 =** を使用してを共有できます。

## <a name="example"></a>例

**Getaddress** の使用例については、「 [_Bstr_t:: Assign](../cpp/bstr-t-assign.md) 」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_bstr_t クラス](../cpp/bstr-t-class.md)
