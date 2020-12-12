---
description: '詳細については、「_bstr_t:: Attach」を参照してください。'
title: _bstr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
ms.openlocfilehash: b3f29c8eaf81a492f7e3c4282227d3d6d246988e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229432"
---
# <a name="_bstr_tattach"></a>_bstr_t::Attach

**Microsoft 固有の仕様**

`_bstr_t` ラッパーを `BSTR` にリンクします。

## <a name="syntax"></a>構文

```cpp
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

**Attach** の使用例については、「 [_Bstr_t:: Assign](../cpp/bstr-t-assign.md) 」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_bstr_t クラス](../cpp/bstr-t-class.md)
