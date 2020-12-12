---
description: '詳細については、「_bstr_t:: copy」を参照してください。'
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: 29ca965730dbcc22b4b725661ece68442d39aeba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229341"
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
の場合、 **`true`** **copy** は含まれているのコピーを返し `BSTR` ます。それ以外の場合は、実際の BSTR **を** 返します。

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
