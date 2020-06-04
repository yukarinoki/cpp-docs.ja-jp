---
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: 8ba42f19e3474cc4a3199771f761b021221f430e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190015"
---
# <a name="_com_ptr_tdetach"></a>_com_ptr_t::Detach

**Microsoft 固有の仕様**

カプセル化されたインターフェイス ポインターを抽出して返します。

## <a name="syntax"></a>構文

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>解説

カプセル化されたインターフェイス ポインターを抽出して返した後、カプセル化されたポインター ストレージを NULL にクリアします。 これによって、カプセル化からインターフェイス ポインターが削除されます。 返されたインターフェイスポインターで `Release` を呼び出すことができます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
