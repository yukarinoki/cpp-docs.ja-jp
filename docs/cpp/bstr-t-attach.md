---
description: '詳細については、「_bstr_t:: Attach」を参照してください。'
title: _bstr_t::Attach
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.openlocfilehash: 02717fad98e4d68dde70995abcfad4cb55b8c45c
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522886"
---
# `_bstr_t::Attach`

**Microsoft 固有の仕様**

`_bstr_t` ラッパーを `BSTR` にリンクします。

## <a name="syntax"></a>構文

```cpp
void Attach(
   BSTR s
);
```

### <a name="parameters"></a>パラメーター

*`s`*\
`BSTR` 変数に関連付けられる、または割り当てられる `_bstr_t`。

## <a name="remarks"></a>解説

`_bstr_t` が以前別の `BSTR` にアタッチされている場合、`_bstr_t` は、`BSTR` の他の変数が `_bstr_t` を使用していない場合 `BSTR` リソースをクリーンアップします。

## <a name="example"></a>例

[`_bstr_t::Assign`](../cpp/bstr-t-assign.md)の使用例については、「」を参照してください **`Attach`** 。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`_bstr_t` 講義](../cpp/bstr-t-class.md)
