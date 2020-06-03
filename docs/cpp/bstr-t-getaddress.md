---
title: _bstr_t::GetAddress
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
ms.openlocfilehash: ca78bd1b607ba4a86bbc824887a7ec767cd5476e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181253"
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

**Getaddress**は、`BSTR`を共有するすべての `_bstr_t` オブジェクトに影響します。 コピーコンストラクターと**演算子 =** を使用して、複数の `_bstr_t` が `BSTR` を共有できます。

## <a name="example"></a>例

**Getaddress**の使用例については、「 [_Bstr_t:: Assign](../cpp/bstr-t-assign.md) 」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_bstr_t クラス](../cpp/bstr-t-class.md)
