---
title: _com_ptr_t::GetInterfacePtr
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetInterfacePtr
helpviewer_keywords:
- GetInterfacePtr method [C++]
ms.assetid: 55e3e2c7-c939-48b5-a905-4b9cbefeea7e
ms.openlocfilehash: 6746cc97696968ca59c2771d79573bd71d86df62
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432476"
---
# <a name="comptrtgetinterfaceptr"></a>_com_ptr_t::GetInterfacePtr

**Microsoft 固有の仕様**

カプセル化されたインターフェイス ポインターを返します。

## <a name="syntax"></a>構文

```
Interface* GetInterfacePtr( ) const throw( ); 
Interface*& GetInterfacePtr() throw();
```

## <a name="remarks"></a>Remarks

NULL にすることがありますが、カプセル化されたインターフェイス ポインターを返します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)