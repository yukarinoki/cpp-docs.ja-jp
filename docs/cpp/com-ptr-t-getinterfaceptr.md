---
title: _com_ptr_t::GetInterfacePtr
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetInterfacePtr
helpviewer_keywords:
- GetInterfacePtr method [C++]
ms.assetid: 55e3e2c7-c939-48b5-a905-4b9cbefeea7e
ms.openlocfilehash: f3244d59159855ff4060c944874e859cb5ec23ab
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170736"
---
# <a name="_com_ptr_tgetinterfaceptr"></a>_com_ptr_t::GetInterfacePtr

**Microsoft 固有の仕様**

カプセル化されたインターフェイス ポインターを返します。

## <a name="syntax"></a>構文

```
Interface* GetInterfacePtr( ) const throw( );
Interface*& GetInterfacePtr() throw();
```

## <a name="remarks"></a>解説

カプセル化されたインターフェイス ポインターを返します。このポインターは NULL である可能性があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
