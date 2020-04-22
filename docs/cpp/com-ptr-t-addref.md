---
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 4dcf643357c9b368d4b2ea3bc51e6567acf45a44
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745095"
---
# <a name="_com_ptr_taddref"></a>_com_ptr_t::AddRef

**マイクロソフト固有**

カプセル化`AddRef`されたインターフェイス`IUnknown`ポインターのメンバー関数を呼び出します。

## <a name="syntax"></a>構文

```cpp
void AddRef( );
```

## <a name="remarks"></a>解説

カプセル`IUnknown::AddRef`化されたインターフェイス ポインターを呼び出`E_POINTER`し、ポインターが NULL の場合はエラーを発生させます。

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
