---
description: '詳細情報: _com_ptr_t::D etach'
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: ec2a18a04b8c32e373225235fd0d6f520e768af0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295511"
---
# <a name="_com_ptr_tdetach"></a>_com_ptr_t::Detach

**Microsoft 固有の仕様**

カプセル化されたインターフェイス ポインターを抽出して返します。

## <a name="syntax"></a>構文

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>解説

カプセル化されたインターフェイス ポインターを抽出して返した後、カプセル化されたポインター ストレージを NULL にクリアします。 これによって、カプセル化からインターフェイス ポインターが削除されます。 返されたインターフェイスポインターに対してを呼び出すことができ `Release` ます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
