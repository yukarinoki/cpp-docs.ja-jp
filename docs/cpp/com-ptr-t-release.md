---
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: cf4cea35386d1f781d6d2946c1730ba2e18dacea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624044"
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release

**Microsoft 固有の仕様**

呼び出し、**リリース**のメンバー関数`IUnknown`カプセル化されたインターフェイス ポインター。

## <a name="syntax"></a>構文

```
void Release( );
```

## <a name="remarks"></a>Remarks

呼び出し`IUnknown::Release`、カプセル化されたインターフェイス ポインターで発生させる、`E_POINTER`このインターフェイス ポインターが NULL の場合のエラー。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)