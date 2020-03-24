---
title: _bstr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
ms.openlocfilehash: 3b52661097ca1feab4c8045be240e4138a0c0f21
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190665"
---
# <a name="_bstr_tattach"></a>_bstr_t::Attach

**Microsoft 固有の仕様**

`_bstr_t` ラッパーを `BSTR` にリンクします。

## <a name="syntax"></a>構文

```
void Attach(
   BSTR s
);
```

#### <a name="parameters"></a>パラメーター

*s*<br/>
`BSTR` 変数に関連付けられる、または割り当てられる `_bstr_t`。

## <a name="remarks"></a>解説

`_bstr_t` が以前別の `BSTR` にアタッチされている場合、`_bstr_t` は、`BSTR` の他の変数が `_bstr_t` を使用していない場合 `BSTR` リソースをクリーンアップします。

## <a name="example"></a>例

**Attach**の使用例については、「 [_Bstr_t:: Assign](../cpp/bstr-t-assign.md) 」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_bstr_t クラス](../cpp/bstr-t-class.md)
