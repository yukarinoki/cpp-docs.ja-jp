---
description: '詳細については、「_bstr_t:: copy」を参照してください。'
title: _bstr_t::copy
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.openlocfilehash: 98726e0c3100851d1496e532310ece2209d71ae0
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522860"
---
# `_bstr_t::copy`

**Microsoft 固有の仕様**

カプセル化された `BSTR` のコピーを生成します。

## <a name="syntax"></a>構文

```cpp
BSTR copy( bool fCopy = true ) const;
```

### <a name="parameters"></a>パラメーター

*`fCopy`*\
の場合、 **`true`** **`copy`** 格納されているのコピーを返し `BSTR` ます。それ以外の場合 **`copy`** は、実際のを返し `BSTR` ます。

## <a name="remarks"></a>解説

パラメーターに応じて、カプセル化されたオブジェクトの新しく割り当てられたコピー、 `BSTR` またはカプセル化されたオブジェクト自体を返します。

## <a name="example"></a>例

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`_bstr_t` 講義](../cpp/bstr-t-class.md)
