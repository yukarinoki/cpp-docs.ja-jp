---
title: _bstr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
ms.openlocfilehash: 718efb9e3dac0d776678fe9efd912a602e041659
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749704"
---
# <a name="_bstr_tattach"></a>_bstr_t::Attach

**マイクロソフト固有**

`_bstr_t` ラッパーを `BSTR` にリンクします。

## <a name="syntax"></a>構文

```cpp
void Attach(
   BSTR s
);
```

#### <a name="parameters"></a>パラメーター

*S*<br/>
`BSTR` 変数に関連付けられる、または割り当てられる `_bstr_t`。

## <a name="remarks"></a>解説

`_bstr_t` が以前別の `BSTR` にアタッチされている場合、`_bstr_t` は、`BSTR` の他の変数が `_bstr_t` を使用していない場合 `BSTR` リソースをクリーンアップします。

## <a name="example"></a>例

**添付**を使用した例については[、_bstr_t::割り当て](../cpp/bstr-t-assign.md)を参照してください。

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[_bstr_t クラス](../cpp/bstr-t-class.md)
