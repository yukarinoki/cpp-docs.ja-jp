---
description: '詳細については、「_com_ptr_t:: AddRef」を参照してください。'
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 0979245662a94596307b1a63af918d0ce67c7b6f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295693"
---
# <a name="_com_ptr_taddref"></a>_com_ptr_t::AddRef

**Microsoft 固有の仕様**

`AddRef` `IUnknown` カプセル化されたインターフェイスポインターでのメンバー関数を呼び出します。

## <a name="syntax"></a>構文

```cpp
void AddRef( );
```

## <a name="remarks"></a>解説

`IUnknown::AddRef`カプセル化されたインターフェイスポインターでを呼び出し、 `E_POINTER` ポインターが NULL の場合はエラーを発生させます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
