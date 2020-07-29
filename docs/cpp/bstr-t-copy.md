---
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: b6029e98e83b171d9ab9f8f3f0282fa3f46ca167
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227596"
---
# <a name="_bstr_tcopy"></a>_bstr_t::copy

**Microsoft 固有の仕様**

カプセル化された `BSTR` のコピーを生成します。

## <a name="syntax"></a>構文

```
BSTR copy( bool fCopy = true ) const;
```

#### <a name="parameters"></a>パラメーター

*fCopy*<br/>
の場合、 **`true`** **copy**は含まれているのコピーを返し `BSTR` ます。それ以外の場合は、実際の BSTR**を**返します。

## <a name="remarks"></a>解説

カプセル化された `BSTR` オブジェクトの新しく割り当てられたコピーを返します。

## <a name="example"></a>例

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_bstr_t クラス](../cpp/bstr-t-class.md)
