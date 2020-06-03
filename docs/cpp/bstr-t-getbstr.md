---
title: _bstr_t::GetBSTR
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
ms.openlocfilehash: da438c65256d9a7e5bf5b02e108fee1385171d2d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181214"
---
# <a name="_bstr_tgetbstr"></a>_bstr_t::GetBSTR

**Microsoft 固有の仕様**

`BSTR` でラップされた `_bstr_t` の先頭を指します。

## <a name="syntax"></a>構文

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>戻り値

`BSTR` でラップされた `_bstr_t` の先頭。

## <a name="remarks"></a>解説

**Getbstr**は、`BSTR`を共有するすべての `_bstr_t` オブジェクトに影響します。 コピーコンストラクターと**演算子 =** を使用して、複数の `_bstr_t` が `BSTR` を共有できます。

## <a name="example"></a>例

**Getbstr**の使用例については、「 [_Bstr_t:: Assign](../cpp/bstr-t-assign.md) 」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_bstr_t クラス](../cpp/bstr-t-class.md)
