---
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 51182b461aeac83c12bb18a573a49b2d4347a190
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189934"
---
# <a name="_com_ptr_taddref"></a>_com_ptr_t::AddRef

**Microsoft 固有の仕様**

カプセル化されたインターフェイスポインターで `IUnknown` の `AddRef` メンバー関数を呼び出します。

## <a name="syntax"></a>構文

```
void AddRef( );
```

## <a name="remarks"></a>解説

は、カプセル化されたインターフェイスポインターで `IUnknown::AddRef` を呼び出し、ポインターが NULL の場合に `E_POINTER` エラーを発生させます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
