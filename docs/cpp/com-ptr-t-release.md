---
description: '詳細については、「_com_ptr_t:: Release」を参照してください。'
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: a1b81295ab249b1826ea6d373f782d91765df3b7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344719"
---
# <a name="_com_ptr_trelease"></a>_com_ptr_t::Release

**Microsoft 固有の仕様**

カプセル化されたインターフェイスポインターでの **Release** メンバー関数を呼び出し `IUnknown` ます。

## <a name="syntax"></a>構文

```cpp
void Release( );
```

## <a name="remarks"></a>解説

`IUnknown::Release`カプセル化されたインターフェイスポインターでを呼び出し、 `E_POINTER` このインターフェイスポインターが NULL の場合はエラーを発生させます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
