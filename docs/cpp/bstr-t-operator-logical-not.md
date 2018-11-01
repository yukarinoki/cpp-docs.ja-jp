---
title: _bstr_t::operator !
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator!
helpviewer_keywords:
- '! operator'
- operator!, bstr
- operator !, bstr
ms.assetid: 6e60b5a5-2d28-4eec-9e12-790da8f1fdd4
ms.openlocfilehash: 3be0ad19260c5b68894e28861ed5bc1635ef4c79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447841"
---
# <a name="bstrtoperator-"></a>_bstr_t::operator !

**Microsoft 固有の仕様**

場合にチェック カプセル化された`BSTR`は、NULL 文字列です。

## <a name="syntax"></a>構文

```
bool operator!( ) const throw( );
```

## <a name="return-value"></a>戻り値

TRUE を返す場合、[はい]、ない場合は FALSE。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_bstr_t クラス](../cpp/bstr-t-class.md)