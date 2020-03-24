---
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: f455e855e782a939e79898ee46e445f65d25d37a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170593"
---
# <a name="_com_ptr_trelease"></a>_com_ptr_t::Release

**Microsoft 固有の仕様**

カプセル化されたインターフェイスポインターで `IUnknown` の**リリース**メンバー関数を呼び出します。

## <a name="syntax"></a>構文

```
void Release( );
```

## <a name="remarks"></a>解説

は、カプセル化されたインターフェイスポインターに対して `IUnknown::Release` を呼び出し、このインターフェイスポインターが NULL の場合、`E_POINTER` エラーを発生させます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
