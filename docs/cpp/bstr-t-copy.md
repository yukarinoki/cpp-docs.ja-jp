---
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: 1fe8cfb5b644b3c7c34cf3325a91ebdf23a04946
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190327"
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
TRUE の場合、 **copy**は含まれている `BSTR`のコピーを返します。それ以外の場合、 **copy**は実際の BSTR を返します。

## <a name="remarks"></a>解説

カプセル化された `BSTR` オブジェクトの新しく割り当てられたコピーを返します。

## <a name="example"></a>例

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_bstr_t クラス](../cpp/bstr-t-class.md)
